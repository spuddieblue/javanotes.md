# Forensic Examination Steps for the Exam

## **Step 1: Creating a Forensic Copy of the Y Drive**
1. **Log into the remote machine on Azure Labs**:
   - **Username**: Use the provided credentials.
   - **Password**: `Forensics2024` (with a capital F).

2. **Start FTK Imager**:
   - Open the FTK Imager application on the remote machine.

3. **Create a forensic copy of the Y drive**:
   - Ensure the Y drive is plugged into the machine (or plug it in if not already connected).
   - In FTK Imager, go to **File > Create Disk Image**.
   - Choose the **source** as the Y drive and proceed.

4. **Generate a forensic image**:
   - Select **Raw (dd)** as the image format.
   - Choose a location to save the image (e.g., a designated folder on the machine).
   - Provide an appropriate name for the image file.

5. **Hashing**:
   - Make sure FTK Imager generates **two hashes**:
     - **MD5**
     - **SHA-1**
   - Write down the **last six digits** of both hashes in your workbook.

---

## **Step 2: Analyzing the Provided Image with Autopsy**
1. **Locate the provided image file**:
   - On the desktop of the remote machine, find the file named `exam_image.00`.

2. **Create a new Autopsy case**:
   - Open the Autopsy application.
   - Create a **new case** and import the `exam_image.00` file.

3. **Recover files from the image**:
   - Use Autopsy to recover **all files** from the provided image.

4. **Extract files**:
   - Extract the recovered files to a designated folder.

5. **Create tags and comments**:
   - Review all the extracted files.
   - Assign **tags** to the files based on their content or significance.
   - Add **appropriate comments** for each file.

6. **Generate an HTML report**:
   - In Autopsy, create an **HTML report** that includes:
     - The recovered files.
     - Tags and comments you have created.

---

## **Final Steps**
- Once completed, **shut down the machine**.
- There is **no need to upload anything to Moodle**. Your report and case will be reviewed later.
