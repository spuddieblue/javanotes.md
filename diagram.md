graph TD;
    A(Start main method) --> B(Initialize Scanner)
    B --> C(Initialize counter = 0)
    C --> D(Display menu)
    D --> E(Read user input)
    
    E -->|1: Increase| F{Call increase(counter)}
    E -->|2: Decrease| G{Call decrease(counter)}
    E -->|3: Display| H{Call display(counter)}
    E -->|4: Exit| I(Exit program)
    
    F --> J(Update counter)
    G --> K(Update counter)
    
    J --> L(Loop back to menu)
    K --> L
    H --> L
    L --> D
    
    I --> M(Close Scanner)
    M --> N(End Program)
