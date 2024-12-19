# Creating a PE File from Scratch with LIEF (Python)

This document provides a step-by-step guide to creating a Portable Executable (PE) file from scratch using the LIEF library in Python.

## Prerequisites

1.  **Python:** Ensure you have Python 3 installed.
2.  **LIEF:** Install the LIEF Python bindings using pip:

    ```bash
    pip install lief
    ```

## Steps

1.  **Import LIEF:** Import the necessary LIEF modules in your Python script:

    ```python
    import lief
    ```

2.  **Create a Binary Object:** This represents the PE file you're creating:

    ```python
    binary = lief.PE.Binary("my_program", lief.PE.PE_TYPE.EXECUTABLE_IMAGE)
    ```

3.  **Create Sections:** You'll need at least a `.text` (code) and a `.data` (data) section:

    ```python
    text_section = lief.PE.Section(".text")
    data_section = lief.PE.Section(".data")
    ```

4.  **Set Section Characteristics:** Define the properties of each section (e.g., executable, readable, writable):

    ```python
    text_section.characteristics = (
        lief.PE.SECTION_CHARACTERISTICS.MEM_READ |
        lief.PE.SECTION_CHARACTERISTICS.MEM_EXECUTE |
        lief.PE.SECTION_CHARACTERISTICS.CNT_CODE
    )

    data_section.characteristics = (
        lief.PE.SECTION_CHARACTERISTICS.MEM_READ |
        lief.PE.SECTION_CHARACTERISTICS.MEM_WRITE |
        lief.PE.SECTION_CHARACTERISTICS.CNT_INITIALIZED_DATA
    )
    ```

5.  **Add Code to the `.text` Section:** This is the most complex part. You'll need raw machine code (bytes). For this example, we'll use a simple return instruction (`0xC3`):

    ```python
    text_section.content = [0xC3]  # Return instruction
    ```

    *   **Important:** For real programs, you'll need to compile assembly code into machine code and then add those bytes here.

6.  **Add Data to the `.data` Section (Optional):** If your program needs initialized data:

    ```python
    data_section.content = [0x01, 0x02, 0x03, 0x04]  # Example data
    ```

7.  **Add Sections to the Binary:**

    ```python
    binary.add_section(text_section)
    binary.add_section(data_section)
    ```

8.  **Set the Entry Point:** This tells the OS where to start executing the code:

    ```python
    binary.entrypoint = text_section.virtual_address  # Start of the .text section
    ```

9.  **Build the PE:** This finalizes the PE structure:

    ```python
    builder = lief.PE.Builder(binary)
    builder.build()
    builder.write("my_program.exe")
    ```

## Complete Example

```python
import lief

binary = lief.PE.Binary("my_program", lief.PE.PE_TYPE.EXECUTABLE_IMAGE)

text_section = lief.PE.Section(".text")
text_section.characteristics = (
    lief.PE.SECTION_CHARACTERISTICS.MEM_READ |
    lief.PE.SECTION_CHARACTERISTICS.MEM_EXECUTE |
    lief.PE.SECTION_CHARACTERISTICS.CNT_CODE
)
text_section.content = [0xC3]  # Return instruction

data_section = lief.PE.Section(".data")
data_section.characteristics = (
    lief.PE.SECTION_CHARACTERISTICS.MEM_READ |
    lief.PE.SECTION_CHARACTERISTICS.MEM_WRITE |
    lief.PE.SECTION_CHARACTERISTICS.CNT_INITIALIZED_DATA
)
data_section.content = [0x01, 0x02, 0x03, 0x04]  # Example data

binary.add_section(text_section)
binary.add_section(data_section)

binary.entrypoint = text_section.virtual_address

builder = lief.PE.Builder(binary)
builder.build()
builder.write("my_program.exe")

print("PE file created successfully!")
