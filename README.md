# Road Map Game Hacking

Because I couldn’t find a clear learning path for Game Hacking, I decided to create one with the help of NotebookLM, an AI that allows you to summarize information from resources you provide. At the end of this post, I include the details of the resources used to develop this learning path.

## 1. Programming Fundamentals

- **C++: The Preferred Language**
    
    - **C++ is highly recommended** for game hacking due to its capability for low-level memory manipulation. This is crucial since it allows hackers to directly access and modify the memory where games store vital information such as player health, ammunition, etc.
    - It is a **compiled** language, meaning that the code is directly translated into machine instructions, resulting in **high performance**, an essential feature for developing cheats that must operate in real time without causing lag.
    - Most **game engines** and the games themselves are written in C++, making it the industry standard for video games. This implies that a deep knowledge of C++ will allow you to better understand how games work and how to interact with them.
    - Although it is considered a difficult language at first due to its complexity, its power and flexibility make it the best tool for game hacking.
    - It is recommended to learn C++ through resources such as **learncpp.com**, which offers text-based tutorials, or the video series by **Cherno** on YouTube.
    - A good command of C++ is necessary to use the Windows API, which is fundamental for game hacking.
    - It is important to note that C++ is the most suitable language to write the core code of a bot (hooks, memory reading) while using Lua (a high-level language) for automation.
- **Python: A Good Starting Point**
    
    - Python is presented as an alternative for beginners due to its **simpler syntax and less steep learning curve**.
    - Being a higher-level language, it allows you to achieve gratifying results more quickly, which can boost the motivation of new programmers.
    - Although C++ is the language of choice for game hacking, Python can be useful for **developing out-of-game bots**, especially in relation to network programming.
    - Experience with Python can make it easier to return to C++ with a new perspective and a better understanding of programming concepts.
- **Fundamental Programming Concepts**
    
    - It is essential to have a solid grasp of **basic programming concepts**, which include:
        - **Functions**: Blocks of code that perform specific tasks and are reusable.
        - **Control Flow**: Structures such as conditionals (if, else) and loops (for, while) that direct the execution of the program.
        - **Pointers**: Variables that store memory addresses, crucial for direct memory manipulation in C++.
        - **Classes**: Templates for creating objects, fundamental in object-oriented programming, which is common in game development.
- **Assembly Language (ASM): The Foundation of Reverse Engineering**
    
    - **Learning to read ASM is fundamental** for game hacking, as it allows you to understand the code at the machine level and how the game directly interacts with the computer’s hardware.
    - Assembly code is the way computers understand a program's instructions. With knowledge of ASM, you can see the low-level version of the code that is executed on the computer, which is very useful for game hacking.
    - When reverse engineering a program, hackers often interact with assembly code.
    - It is not necessary to become an expert in writing ASM, but you should be able to read and interpret the code to understand a program's internal workings.
    - Tools like **OllyDbg**, **x64dbg**, and **IDA Pro** allow you to analyze assembly code.
    - The ability to read ASM is also useful for understanding techniques like NOPing and hooking.
    - It is recommended to practice reverse engineering your own C++ programs to understand how high-level code translates into ASM.
    - There are various online resources available for learning assembly.

## 2. Reverse Engineering

- **Reverse engineering** is a fundamental process in game hacking that involves **disassembling a program (such as a video game) to understand how it works internally**. This is crucial because game hackers do not have access to the game's original source code. Instead, they work with the compiled (binary) code, which is difficult to understand directly. The goal is to **discover vulnerabilities and comprehend the game's logic**, which is essential for developing hacks or bots.
    
- **Purpose of Reverse Engineering:**
    
    - **Understand the structure and execution flow of the game.**
    - **Identify the location of important variables in memory** (such as health, ammunition, position, etc.).
    - **Discover useful functions, classes, and variables** for manipulating the game.
    - **Find vulnerabilities** to exploit and create hacks.
    - **Reconstruct the program's logic** and understand how it interacts with the system and the network.
    - **Create custom tools** for analyzing and manipulating the game.
- **Types of Analysis in Reverse Engineering:**
    
    - **Static Analysis:** This type of analysis is performed **without running the program**. It involves examining the binary code, its structure, the libraries it uses, and other aspects of the file.
        - The assembly code is inspected to understand the program's logic.
        - Text strings (strings) that may give clues about the program's functionality are identified.
        - The file header information (such as the PE format in Windows) is analyzed to understand its dependencies and characteristics.
        - Tools such as disassemblers and PE file analyzers are used to examine the code without executing it.
        - It allows for **identifying potential vulnerabilities** without the risks associated with running the code.
        - It serves as a starting point for analysis, as static information can be quickly obtained without executing the program.
        - In malware analysis, static information helps identify malicious infrastructure or compressed files.
    - **Dynamic Analysis:** This type of analysis is performed **by executing the program in a controlled environment** (such as a virtual machine). The behavior of the program is observed during execution to understand its functionality.
        - **Debuggers** are used to control the program's execution line by line, observe changes in memory and registers, and set breakpoints.
        - It allows for identifying how the program interacts with the system (files, registry, network).
        - It is used to confirm functionalities and handle encryption or payloads.
        - It helps **uncover the logic of an algorithm** or hidden functions within the program.
        - It aids in finding **paths to dynamic memory pointers**.
        - In malware analysis, it is used to observe malicious behavior and how it evades the sandbox.
- **Hybrid Analysis:** Combines static and dynamic analysis techniques to obtain a more complete picture, as some malware hides its presence and may be detected using hybrid analysis.
    
- **Key Tools for Reverse Engineering:**
    
    - **Disassemblers:**
        - **IDA Pro:** A very popular tool in the security industry, known for its ability to disassemble code across different architectures (x86, ARM). It allows for generating flowcharts, supports scripting, and with its Hex-Rays plugin, can even generate equivalent C code. A limited free version is available. It is considered one of the best disassemblers and decompilers on the market.
        - **Ghidra:** A **free and open-source** alternative maintained by the NSA. It offers capabilities similar to IDA Pro, including disassembly, decompilation, and scripting. It is a powerful tool for analyzing compiled code.
        - **Hopper:** A disassembler for macOS and Linux.
        - **Radare2:** A reverse engineering framework that acts as a forensic tool, hex editor, binary analyzer, disassembler, and debugger.
    - **Debuggers:** Allow for the **controlled execution of the program** to observe its real-time behavior.
        - **x64dbg:** An open-source debugger for Windows that can debug both 32-bit and 64-bit applications. It is very popular among game hackers.
        - **OllyDbg:** An assembly-level debugger very useful for game analysis. It is known for its portability and range of functions. It can be extended with plugins for additional capabilities.
        - **WinDbg:** Microsoft's official debugger for Windows, useful for debugging both user-mode and kernel-mode code. It can load memory dumps and symbols to facilitate analysis.
        - **GDB (GNU Debugger):** Originally a debugger for Linux, but also used for Windows. It supports high-level languages such as C, C++, and Java.
        - **Immunity Debugger:** An enhanced version of OllyDbg with support for Python plugins.
    - **Memory Analysis Tools:**
        - **Cheat Engine:** A versatile tool for **scanning and modifying a game's memory**. It also includes a basic debugger and disassembler. It is ideal for beginners due to its ease of use. It allows for creating cheat tables that can be shared with other users.
        - **ReClass.NET:** Used to visualize and **reconstruct data structures in memory**, showing how bytes are interpreted as different data types. It is useful for organizing and understanding large blocks of memory.
    - **Other Tools:**
        - **HxD:** A basic hexadecimal editor.
        - **CFF Explorer:** A PE file viewer that extracts important information from executables.
        - **Process Monitor and Process Explorer:** Tools that allow monitoring a process's actions, such as interactions with files, registries, and other processes.
- **Anti-Reverse Engineering Techniques:** Software creators (including malware developers) use techniques to hinder the reverse engineering process. Some of these techniques include:
    
    - **Code obfuscation:** Makes the code harder to understand.
    - **Anti-debugging:** Detects when the program is being run in a debugger and alters its behavior.
    - **Anti-disassembly:** Uses tricks to confuse disassemblers, hiding valid instructions.
    - **Encryption:** Malware can encrypt its own code or data.
- **Importance of Knowing Assembly:** For thorough analysis, it is necessary to understand assembly language. The disassembler converts machine code into assembly mnemonics, and it is essential to learn how to read assembly code to understand what the software is actually doing at a low level.


## 3. Memory Manipulation

- **Fundamental Concept:** Memory manipulation is an essential technique in game hacking that involves **reading and writing data in the memory of a running process (specifically a video game)**. A game's memory contains a numerical representation of its state, such as the player's health, position, amount of money, etc. Hackers use memory manipulation to alter these values and thereby modify gameplay.
    
- **Objectives of Memory Manipulation:**
    
    - **Find and modify game values:** Locate the memory address where data such as health, ammunition, or score is stored, and change these values.
    - **Create cheats and hacks:** Automate actions like increasing health, ammunition, or teleporting across the map.
    - **Develop bots:** Programs that can play the game automatically, performing tasks such as healing, attacking, or gathering resources.
    - **Understand the game's state:** Obtain a numerical representation of the game's variables that allows for intelligent interaction.
    - **Customize the game experience:** Enable players to modify aspects of the game to their liking.
- **Main Tools for Memory Manipulation:**
    
    - **Cheat Engine:** An open-source tool widely used for memory manipulation in games. It allows you to:
        - **Scan memory:** Search for specific values in a process's memory.
        - **Modify values in real time:** Directly change the data found in memory.
        - **Create cheat tables:** Save memory addresses and their values for future sessions.
        - **Generate trainers:** Automate the modification of values through keyboard shortcuts.
        - **Perform pointer scanning:** Find chains of pointers that lead to dynamic memory addresses.
        - **Use Lua Scripting:** Automate complex memory manipulation tasks through scripts.
    - **OllyDbg:** An assembly-level debugger that allows for deeper analysis of a game's memory. It helps identify pointers by tracing execution and enables examination of the game's assembly code.
    - **ReClass.NET:** Allows visualization of memory blocks as data types, facilitating the reconstruction of data structures.
    - **Process Monitor and Process Explorer:** Tools that enable you to monitor a process's actions, including its memory interactions, making it easier to identify areas of interest in memory.
- **Memory Scanning Process with Cheat Engine:**
    
    1. **Attach Cheat Engine to the game process:** Select the game process whose memory you want to modify.
    2. **Perform a first scan (First Scan):** Search the process's memory for values that match a known value. For example, if you know your current health (e.g., 100), you search for the value 100.
    3. **Filter the results (Next Scan):** Change the value in the game (for example, damage the character so that health changes), then perform a new scan to find the memory addresses that changed. This process is repeated until the required memory address is found.
    4. **Determine the correct address:** In some cases, you need to experiment by manually modifying the values of the remaining addresses until you find the one that affects the desired value.
    5. **Add the address to the cheat table:** Save the found addresses and their values to facilitate future use.
    6. **Modify the memory:** Change the value saved in the cheat table directly, or create a trainer to automate the modification.
    7. **Freeze values:** Ensure that a value does not change by repeatedly writing the same value to the memory address.
- **Types of Scans:** Cheat Engine allows different types of scans, including:
    
    - **Exact Value:** Searches for values that exactly match the entered value.
    - **Increased Value:** Searches for values that have increased since the previous scan.
    - **Decreased Value:** Searches for values that have decreased since the previous scan.
    - **Value Between:** Searches for values that are within a specific range.
    - **Unknown Initial Value:** Searches for values that have changed without knowing their previous value.
- **Static vs. Dynamic Addresses:**
    
    - **Static Addresses:** These are memory addresses that remain constant during the game's execution and between sessions. They are ideal for creating long-lasting hacks since they do not change. In Cheat Engine, static addresses are usually shown in green.
    - **Dynamic Addresses:** These are memory addresses that change every time the game is started. To access these values, pointers and pointer scanning are used. In Cheat Engine, dynamic addresses are usually shown in black.
- **Pointer Scanning:**
    
    - **Pointers** are memory addresses that point to other addresses. A **pointer chain** is a series of pointers that, when followed one after the other, lead to the memory address containing a value of interest.
    - **Pointer scanning** allows you to find these chains that lead to dynamic memory addresses. This is crucial in games that store values dynamically.
    - To perform a pointer scan in Cheat Engine, right-click on a dynamic address and choose "Pointer scan for this address."
    - Cheat Engine offers various options to optimize pointer scanning, including limiting the chain length, searching only for static pointers, and avoiding read-only addresses.
- **Importance of Pointers:**
    
    - Pointers are essential for accessing dynamic memory since these addresses change every time the game is started.
    - They allow you to access information in a stable manner, as long as the initial pointer in the pointer chain is static.
- **Other Important Aspects of Memory Manipulation:**
    
    - Values in memory are stored with specific data types such as integers, floats, etc.
    - Data structures organize the information, and by understanding them, large blocks of memory can be manipulated with a single address.
    - It is crucial to understand the difference between code and data in memory.
    - Games may use obfuscation techniques to hide values in memory.
    - Memory protection (such as ASLR - Address Space Layout Randomization) makes memory manipulation more difficult and requires bypass techniques.


## 4. Windows API (WinAPI)

- **Fundamental Concept:** The Windows API (WinAPI), also known as the Win32 API, is a set of **functions and data structures** provided by the Windows operating system that allows software developers to interact with it. These APIs enable programs to perform a wide variety of tasks, from memory management to creating graphical user interfaces, as well as network communication and file manipulation. In the context of _game hacking_, the WinAPI is essential because it offers the necessary tools to **manipulate the processes and memory of other programs**, including video games.
    
- **Importance in Game Hacking:** The WinAPI is fundamental for game hacking because it provides the low-level functions needed to:
    
    - **Access and modify the memory of other processes:** Functions like `ReadProcessMemory` and `WriteProcessMemory` allow hackers to read and write data in the memory of other processes, which is essential for modifying game values.
    - **Inject code into other processes:** Functions such as `VirtualAllocEx` and `CreateRemoteThread` enable hackers to inject and execute code in other processes, which is used to introduce hacks or bots into games.
    - **Debug processes:** The debugging functions of the WinAPI can be used to analyze a program's behavior, detect vulnerabilities, and understand how it works internally.
    - **Monitor events:** It allows hackers to monitor system events, such as keystrokes or window messages, which is useful for creating keyloggers or detecting user actions.
    - **Manage processes and threads:** It enables hackers to create, manipulate, and terminate processes and threads, which is fundamental for controlling how a program interacts with the system.
- **Key WinAPI Functions for Game Hacking:**
    
    - **`ReadProcessMemory`:** Allows reading data from a specific address in another process's memory. This function takes as arguments a handle to the target process, the memory address to read from, a buffer to store the read data, and the size of the data to be read.
    - **`WriteProcessMemory`:** Allows writing data to a specific address in another process's memory. Similar to `ReadProcessMemory`, this function takes a handle to the target process, the memory address to write to, a buffer with the data to write, and the size of the data to be written.
    - **`VirtualAllocEx`:** Allows reserving memory in the virtual memory space of another process. Essential for code injection, this function takes a handle to the target process, the starting address for the memory, the size of the memory to reserve, and the desired protection type.
    - **`CreateRemoteThread`:** Allows creating a new thread of execution in another process. This function takes a handle to the target process, a pointer to the function that the new thread will execute, and arguments for that function. It is used in code injection to start the execution of the injected code.
    - **`OpenProcess`:** Allows obtaining a handle to a running process, necessary for using other functions such as `ReadProcessMemory`, `WriteProcessMemory`, and `VirtualAllocEx`. This function takes the process identifier (PID) as an argument.
    - **`CloseHandle`:** Allows closing a previously opened handle, freeing the associated system resources. It is important to close handles when they are no longer needed to avoid memory leaks.
    - **`GetWindowThreadProcessId`:** Retrieves the process ID associated with a specified window.
    - **`FindWindow`:** Obtains the handle of a window based on its title. It is used to get the game’s handle and, from it, the PID.
    - **`GetProcAddress`:** Retrieves the address of a function exported from a dynamic link library (DLL). It is used to get the entry point of API functions.
    - **`LoadLibrary`:** Loads a DLL into the current process's address space. It is frequently used for DLL injection.
    - **`VirtualProtect`:** Changes the protection of a region of memory, for example, to allow writing to a region that was originally read-only. It is essential for code injection and memory manipulation.
    - **`GetAsyncKeyState`:** Determines if a key is pressed. It is used by keyloggers to record keystrokes.
- **Debugging, Toolhelp, and Hooking Functions:**
    
    - **Debugging Functions:** The WinAPI provides functions that allow a debugger to control a process's execution, set breakpoints, inspect variables, etc. These functions are fundamental for malware analysis and reverse engineering.
    - **Toolhelp Functions:** This set of functions allows enumerating and obtaining information about processes, threads, modules, and heaps in the system. They are useful for obtaining information about the system’s state and the resources used by a process.
    - **Hooking Functions:**
        - Hooking is a technique that intercepts calls to specific functions (such as WinAPI functions), allowing the hacker to execute their own code before, after, or instead of the original function.
        - This is used to log events, modify a program’s behavior, or inject malware.
        - Hooks can be local (applied to a single process) or global (applied system-wide).
        - There are different types of hooking:
            - **API Hooking:** Based on modifying a process's Import Address Table (IAT).
            - **DLL Injection:** Involves injecting a DLL into a process to change its behavior. Once injected, the DLL can act as an API that allows external access and interaction with the process.
            - **Low-level Message Hooking:** Based on monitoring keyboard and mouse messages at the operating system level to record user actions.
            - **Virtual Function (VF) Hooking:** Based on intercepting calls to virtual functions of classes to modify their behavior.
- **Importance of DLLs (Dynamic-Link Libraries):**
    
    - DLLs are code libraries that contain functions and resources that can be shared by multiple programs.
    - The WinAPI is primarily implemented through DLLs.
    - DLLs can be dynamically loaded by a process at runtime, making them a common vector for code injection.
    - DLL injection allows modifying a process’s behavior from within, as the injected code has access to the process’s memory and other resources.
- **Creating Basic Windowed Programs:**
    
    - Learning to create basic windowed programs in Windows helps to understand how events and messages work.
    - Windowed programs send and receive messages that indicate what actions the application should perform (for example, when a user clicks a button or types in a text box).
    - This understanding is useful for manipulating a game's interface or intercepting events that occur within it.
    - To create windowed programs, functions of the WinAPI that handle windows are used, such as `CreateWindowExW`, `RegisterClassExW`, `ShowWindow`, and `UpdateWindow`.
- **Common WinAPI Libraries:**
    
    - **KERNEL32.DLL:** Contains core system functions, file management, memory, processes, and threads.
    - **USER32.DLL:** Contains functions for managing the graphical user interface (windows, menus, messages, etc.).
    - **ADVAPI32.DLL:** Contains functions related to the Windows registry and services.
    - **MSVCRT.DLL:** Contains standard functions from the C runtime library, such as `printf`, `scanf`, `malloc`, etc.
    - **WS2_32.DLL, WININET.DLL, URLMON.DLL, NETAPI32.DLL:** Contain functions for network and internet communication.
    - **NTDLL.DLL:** Contains native functions that interact directly with the system kernel.
- **Additional Considerations:**
    
    - The WinAPI is documented in the MSDN Library (Microsoft Developer Network).
    - It is useful to know the parameters of each function, their return values, and potential errors.
    - The WinAPI can be used from different programming languages that can handle low-level data structures.
    - There are many undocumented APIs that are used by malware to hide their behavior.

## 5. Code Injection and DLLs

- **General Concept:** Code injection is a technique that allows **executing arbitrary code within the memory space of another process**, such as a video game. In the context of _game hacking_, this means that a hacker can inject their own code into the game, giving them significant control over its behavior. DLL injection is a common way to achieve code injection.
    
- **Importance in Game Hacking:**
    
    - Code injection is a powerful technique that enables hackers to modify a game from the inside.
    - By executing code in the context of the game’s process, the injected code can access the game’s memory, its internal functions, and other resources.
    - This allows for very complex modifications, such as creating bots, altering gameplay, or implementing additional functionalities.
    - Code injection can also be used to implement hacks that provide unfair advantages to players, such as wallhacks or aimbots.
    - Code injection can be used for legitimate purposes as well, such as debugging or enhancing a game.
- **DLL Injection (Dynamic Link Libraries):**
    
    - DLLs are files that contain code and data that can be shared by multiple programs.
    - DLL injection consists of forcing a process to load a specific DLL into its memory space.
    - Once a DLL has been injected into a process, its code can be executed within that process.
    - This technique is commonly used in game hacking because it is easier to write code in C++ and compile it as a DLL than to write low-level shellcode.
    - The injected DLL becomes part of the target process, gaining access to its memory and resources.
- **DLL Injection Methods:**
    
    - **Using `LoadLibrary`:** A common way to inject a DLL is by using the WinAPI function `LoadLibrary`.
        - A hacker can use a code cave to **call the `LoadLibrary` function** within the target process and force it to load a malicious DLL.
    - **Thread Injection:** A new thread of execution is created in the target process, which calls the `LoadLibrary` function to load the DLL.
        - The `CreateRemoteThread` function can be used to create this new thread.
    - **Hijacking:** The main thread of the process is modified to execute a code cave that loads the DLL.
        - The main thread is "frozen" and its execution is redirected to the code cave that calls `LoadLibrary` to load the DLL.
- **General Code Injection Process:**
    
    1. **Locate the target process:** Identify the process into which the code will be injected.
    2. **Obtain a handle to the target process:** Use the `OpenProcess` function to acquire the handle.
    3. **Reserve memory in the target process:** Use the `VirtualAllocEx` function to reserve memory in the target process's virtual memory.
    4. **Write the code (or the DLL path) into the reserved memory:** Use the `WriteProcessMemory` function to copy the code or the DLL path into the reserved memory of the target process.
    5. **Execute the injected code:** Use `CreateRemoteThread` or `QueueUserAPC` to force the target process to execute the injected code.
- **Code Caves:**
    
    - A code cave is a fragment of memory within the target process that contains shellcode used to perform actions such as calling `LoadLibrary`.
    - Code caves can be used to inject code or to modify the control flow of the process.
- **Use of a "Trainer":**
    
    - A trainer is a tool used to modify games, often utilizing DLL injection.
    - A trainer attaches to a game's process and listens for key presses associated with the functionality of hotkeys.
    - When a key press is detected, the trainer executes the associated functionality through the backdoor API of the injected DLL.
    - The trainer can inject a DLL that acts as a backdoor API, allowing modification of the game’s memory or the functions that the game executes.
    - A trainer can be packaged as a portable executable that can be run after the game has launched to attach the trainer to the game.
- **Important Considerations:**
    
    - Code injection is a powerful technique, but it can also be dangerous if used for malicious purposes.
    - Injecting code or DLLs requires elevated permissions from the operating system, which can pose a security risk if using tools from untrusted sources.
    - It is essential to exercise caution when using trainers or hacking tools that are not trustworthy, as they may contain malware.
    - Some games have anti-cheat protections that can detect or prevent code injection.
    - The code injected into a process can directly access and modify the process's memory without needing to use `ReadProcessMemory` or `WriteProcessMemory`.
    - When injecting a DLL, it is important to assign it a unique name to avoid conflicts with other system DLLs.
    - It is important to close handles to any created threads to avoid memory issues.
    - Using a debugger can be helpful to test and debug the code injected into a process.
    - To prevent the injected DLL from being affected by ASLR (Address Space Layout Randomization) protection, it is advisable to disable it or use techniques to bypass it.
    - In some cases, it may be necessary to use functions like `VirtualProtect` to be able to write to memory regions that are read-only.
    - The code injected into a process can also obtain the base address of the process's main module to access its data using assembly techniques.

## 6. Hooking Techniques

- **General Concept:** Hooking is a technique that allows **intercepting and modifying a program’s execution flow by redirecting calls to specific functions to a function defined by the hacker**. This is achieved by modifying the code or the function address tables so that, instead of executing the original function, the hook code is executed first.
    
- **Purpose of Hooking:**
    
    - **Function Interception:** The main goal of hooking is to intercept function calls, whether they are from the Windows API (WinAPI), the Direct3D API, or internal functions of the game itself.
    - **Behavior Modification:** Once a function call is intercepted, its behavior can be modified, the input or output parameters can be altered, or its execution can be prevented altogether.
    - **Analysis and Monitoring:** Hooking is also used to analyze a program’s behavior, track its function calls, and gather information about its operation.
    - **Implementing Additional Features:** In game hacking, hooking enables the addition of new features to a game, such as wallhacks, aimbots, or bots.
- **Types of Hooking:**
    
    - **API Hooking:**
        - **Objective:** Intercept calls to Windows API functions, such as `CreateProcess`, `LoadLibrary`, `ReadProcessMemory`, `WriteProcessMemory`, `TextOutA`, or network functions like `send` and `recv`.
        - **Methods:**
            - **IAT Hooking (Import Address Table):** The import table of a module is modified so that calls to API functions are directed to the hook instead of the original function.
                - This is useful for intercepting calls to Windows APIs on a per-module basis.
            - **Inline Hooking:** The original function’s code is modified, usually at the beginning of the function, by inserting a jump to the hook function, which will execute the desired code and then may execute (or not) the original function.
                - This requires modifying the memory where the function resides, which may require changing its permissions using functions like `VirtualProtect`.
                - Sometimes, the first few bytes of the original function are copied into a trampoline function, which, after executing the original code, returns control to the hook.
        - **Trampoline:** A trampoline is a small function that saves registers, calls the original function, and restores the registers. It is used in inline hooking to ensure that the original function executes correctly.
        - **Uses:**
            - Hiding the presence of malware.
            - Modifying the behavior of API functions.
            - Redirecting calls to other functions.
            - Intercepting drawing function calls such as `TextOutA` in a game.
            - Monitoring API usage by a program.
    - **Direct3D Hooking:**
        - **Objective:** Intercept and modify calls to Direct3D API functions, a graphics API used by many games.
        - **Methods:**
            - **VF Table Hooking (Virtual Function Table):** The virtual function table of a Direct3D object is modified so that calls to specific functions, such as `EndScene()` or `Reset()`, are directed to the hook function.
            - **Jump Hooking:** A jump is inserted at the beginning of a Direct3D function to redirect execution to the hook function, which is useful when VF Table Hooking cannot be used.
        - **Uses:**
            - Creating wallhacks that allow seeing through walls.
            - Modifying game lighting.
            - Adding extra information on the screen (HUDs).
            - Creating custom graphic effects.
    - **Kernel Mode Hooking:**
        - **Objective:** Intercept calls to the operating system kernel functions.
        - **Methods:**
            - **SSDT Hooking (System Service Descriptor Table):** The system service descriptor table is modified so that calls to kernel functions are directed to the hook.
                - This can be used to hide the presence of malware.
            - **Code Patching:** The code of kernel functions is modified to redirect execution.
        - **Uses:**
            - Hiding processes, files, or registry entries.
            - Intercepting calls to memory management or system access functions.
    - **Other Techniques:**
        - **Call Hooking:** Modifying the destination address of a CALL instruction so that execution is redirected to the hook function.
        - **Keyboard Message Hooking:** Using the `SetWindowsHookEx` function to intercept keyboard messages and log keystrokes.
        - **Network Packet Function Hooking:** To intercept data sent and received by a game, the functions responsible for processing network packets can be hooked.
- **Tools for Hooking:**
    
    - **API Monitor:** A tool for monitoring and analyzing Windows API calls.
    - **Deviare API Hook:** A hooking engine for Win32 functions and COM objects.
    - **Microsoft Detours:** A library for Win32 API hooking based on jump hooks.
    - **MadCHook:** Another hooking library that detects and tracks other hooks.
    - **GMER/Ring3 API Hook Scanner:** Tools for detecting hooks in a system.
- **Implementing a Hook:**
    
    1. **Identify the Target Function:** Determine the specific function to be hooked.
    2. **Create the Hook Function:** Develop the code that will be executed when the target function is intercepted.
    3. **Modify the Target Function:** Insert the hook into the target function, either through IAT hooking or inline hooking.
    4. **Call the Original Function (Optional):** Within the hook function, decide whether or not to call the original function.
    5. **Manage the Stack and Registers:** Ensure that the hook function correctly handles the stack and preserves registers to avoid program errors.
    6. **Restore the Original State (if necessary):** In inline hooking, it is necessary to restore the original function after the hook function has completed its work.
- **Important Considerations:**
    
    - Hooking is a powerful technique that can be used for malicious purposes, such as creating rootkits that hide malware.
    - It is important to note that some games have anti-cheat protections that can detect and prevent the use of hooks.
    - Some Windows API functions have additional protections that make hooking more difficult.
    - Hooking can cause stability issues if not implemented correctly.
    - Advanced techniques and special permissions are required for kernel hooks.

## 7. Bot Development

- **General Concept:** Bot development involves creating programs that **automate actions within a game**. These bots can range from simple assistants to complex programs capable of playing autonomously. The key to their development lies in combining memory manipulation techniques, hooking, and input simulation, along with principles from control theory, state machines, and search algorithms.
    
- **Key Components in Bot Development:**
    
    - **Memory Manipulation:**
        - **Memory Scanning:** Bots use tools like Cheat Engine to **search for memory addresses where important game data is stored**, such as health, position, money, etc.
        - **Memory Modification:** Once these addresses are found, the bot can **read and write values in the game's memory** to alter its behavior. For example, a bot might modify its health or the amount of money it has.
        - **Static Pointers:** Bots must use static pointers that always point to the player's memory location, because memory addresses may change every time the game is restarted.
    - **Hooking:**
        - **Function Interception:** Bots use hooking to **intercept function calls** from the game or the operating system. This allows them to control the game’s execution flow and modify its behavior.
        - **Behavior Modification:** By intercepting a function, the bot can **alter the parameters, the results, or the behavior of the function**, which enables the addition of new functionalities or the modification of existing ones. For example, hooking a drawing function can be useful for creating a wallhack.
    - **Input Simulation (Keyboard and Mouse):**
        - **Action Emulation:** Bots need to simulate actions that a human player would perform, such as pressing keys or moving the mouse. To do this, operating system functions like `SendInput()` or `SendMessageA()` are used.
        - **Task Automation:** By simulating these actions, the bot can **automate repetitive tasks** or react to events within the game.
        - **Avoiding Detection:** It is important to use all keyboard messages (WM_KEYDOWN, WM_CHAR, WM_KEYUP) to avoid the bot being detected.
    - **Control Theory:**
        - **Feedback:** Bots should implement feedback loops where sensors (memory reading, hooks) are used to obtain the game state, and a controller makes decisions and takes actions. This is based on control theory, which allows bots to act based on the information obtained.
        - **Error Correction:** Bots can also implement error correction mechanisms to adjust to unforeseen situations and improve their behavior. For example, a healing bot might adjust its behavior if it detects that its healing did not have the desired effect.
    - **State Machines:**
        - **Organizing Behavior:** State machines allow a bot’s behavior to be organized into **different states**, where each state represents a specific task. For example, a bot might have one state for searching for enemies, another for attacking them, and another for picking up loot.
        - **Transition Between States:** The bot **transitions between states** based on game events or decisions made by the controller.
        - **Healer Bots:** A healer bot might have a "low health" state that triggers taking a potion and then transitions back to a "normal health" state.
        - **Flexibility:** State machines can be modified and combined with control theory to achieve the desired outcomes.
    - **Search Algorithms:**
        - **Pathfinding:** Bots need search algorithms to find optimal paths, for example, in game maps. One example is the A* algorithm.
        - **Target Selection:** Search algorithms are also used to find the nearest enemy or the shortest route to collect items.
        - **Action Optimization:** Search algorithms help optimize the bot’s actions in its quest for objectives.
- **Programming Languages:**
    
    - **C++:** A language widely used for bot development due to its capability for low-level memory manipulation.
    - **Lua:** A high-level language that can be embedded in C++ programs for task automation. It is very useful for adding flexibility to the bot.
- **Types of Bots:**
    
    - **Reactive Bots:**
        - **Event Response:** These bots **react to events** within the game, such as a drop in the player’s health or the appearance of an enemy.
        - **Examples:** Autohealers (bots that automatically use potions when health is low), autocombo bots (bots that perform combined attacks automatically).
        - **Techniques:** They use hooks to detect events, memory modifications to obtain the game state, and input simulation to execute actions.
    - **Autonomous Bots:**
        - **Full Automation:** These bots **can play an entire game without human intervention**.
        - **Examples:** Cavebots (bots that explore caves and collect loot), warbots (bots that battle against other players).
        - **Techniques:** They use control theory, state machines, and search algorithms to make decisions and take actions.
        - **Actions:** They can heal themselves, pick up loot, walk, sell items, buy supplies, etc.
    - **Clicker Bots:** Simple bots that execute repetitive actions using keyboard and mouse simulation. They do not interact directly with the game’s memory. They are easy to create but tend to be less reliable.
- **Additional Considerations:**
    
    - **Bot Detection:** Game developers use anti-cheat software to detect bots by monitoring unusual behaviors, such as extremely precise movements or repetitive patterns.
    - **Evasion of Detection:** Bot developers use techniques to avoid detection, such as randomizing actions or simulating human-like movements.
    - **Server Interaction:** Some bots can interact directly with the game server, simulating a legitimate game client.
    - **Scripts:** Bots should have the ability to execute scripts so that users can add support for new functionalities and customize their behavior.
- **Practical Example (Healing Bot):** A healing bot could work as follows:
    
    1. **Memory Reading:** The bot reads the memory address where the character’s health is stored.
    2. **Condition:** If the health is below a certain value (for example, 500), the bot executes the following action.
    3. **Action Simulation:** The bot simulates pressing the healing button.
    4. **Repetition:** The bot continuously repeats this cycle.
- **Tools for Bot Development:**
    
    - **Cheat Engine:** For searching and modifying memory addresses.
    - **OllyDbg and x64dbg:** For debugging and analyzing game behavior.
    - **Process Monitor:** For monitoring a process’s actions, such as file access, registry, and system interactions.
    - **Visual Studio:** An IDE for writing C++ code.
    - **AutoIt and AutoHotKey:** Scripting languages for automation and input simulation.
    - **DirectX SDK:** For graphics hooking.

## 8. Anti-Cheat Evasion

- **General Concept:** Anti-cheat systems are programs designed to **detect and prevent the use of cheats and bots in games**. These systems employ a variety of techniques to identify suspicious activities and, as a result, take actions such as kicking the player or permanently banning the account. Evasion of anti-cheat is a **constant "cat and mouse" game** where bot developers look for ways to bypass detection, while game developers improve their anti-cheat systems.
    
- **Anti-Cheat Detection Techniques:** Anti-cheat systems use various techniques, which can be classified as follows:
    
    - **Signature-Based Detection (SBD):**
        - **Searching for Specific Code:** Anti-cheat systems **search for code fragments** or binary patterns known to be associated with bots or cheats. It is similar to how antivirus software looks for malware signatures.
        - **Vulnerability:** This technique is vulnerable to **code obfuscation** and modifications of the bot’s binaries.
    - **File Integrity Verification:**
        - **File Validation:** The anti-cheat system **checks that the game files have not been modified** by users. This is done by generating hashes of the files and comparing them with predefined values.
        - **Evasion:** To evade this technique, one can **modify the file and change the corresponding hash**.
    - **DLL Injection Detection:**
        - **Monitoring:** The anti-cheat system **detects when dynamic link libraries (DLLs) are injected** into the game's process, a common technique for introducing third-party code.
        - **Deception:** Hackers may try to hide the DLL injection by using a "wrapper."
        - **Legitimate Use:** It is important to note that DLL injection is not necessarily malicious. It is also used by accessibility tools or for debugging purposes.
    - **Hook Detection:**
        - **Call Monitoring:** The anti-cheat system **detects when system or game function calls are intercepted (hooked)**. Hooks are a commonly used technique to modify a program’s behavior.
        - **Evasion:** One can try to avoid hook detection by using **obfuscation techniques** or hooking at lower levels of the system.
    - **Memory Monitoring:**
        - **Change Analysis:** The anti-cheat system **analyzes the game’s memory for suspicious changes** or access patterns that indicate bot usage.
        - **Read and Write Blocking:** The anti-cheat system may block memory read and write functions.
        - **Evasion:** Techniques such as **data obfuscation** and pointer modification are used to evade this detection.
        - **Memory Spoofing:** Hackers may try to deceive the anti-cheat system by spoofing memory, although this is more difficult if done from a kernel-mode driver.
    - **Debugger Detection:**
        - **Debugger Search:** The anti-cheat system **detects if a debugger is attached** to the game’s process. A debugger is a programming tool that allows step-by-step examination of a program’s execution.
        - **Evasion:** Anti-debugging techniques can be used to **hide the presence of a debugger**.
    - **Sandbox and Virtual Machine (VM) Detection:**
        - **Environment Identification:** The anti-cheat system tries to **identify if the game is running in an isolated environment** (such as a sandbox or VM), as these environments are common for analyzing malware or running bots.
        - **Evasion:** Anti-analysis techniques are used to **avoid detection in virtual environments**, as these can be used by bot developers or malware analysts.
    - **Behavioral Analysis:**
        - **Suspicious Patterns:** Anti-cheat systems use **artificial intelligence and machine learning** to detect suspicious behavior patterns characteristic of bots, such as extremely precise movements, extremely fast response times, or the execution of repetitive sequences of actions.
    - **Heuristics:**
        - **Internal Pattern Analysis:** The anti-cheat system **analyzes program characteristics for internal patterns** that may indicate that it is a bot. It assigns a score to each pattern, and if the total score exceeds a certain threshold, the program is considered a bot.
        - **Evasion:** It is important for bots to **emulate human behavior** to evade these analyses.
    - **Screenshot Capture:**
        - **Image Acquisition:** The anti-cheat system may **take screenshots of the game** to visually detect the use of cheats such as wallhacks or aimbots.
        - **Evasion:** Bots may try to **avoid screenshot capture** or even alter the screenshots.
    - **Network Traffic Analysis:**
        - **Pattern Detection:** The anti-cheat system can **analyze network traffic patterns** to detect suspicious activities that may indicate bot usage.
        - **Packet Interception:** The anti-cheat system can **detect if network packets are being intercepted** to read and manipulate game information.
        - **Encryption:** Encryption is used to protect game traffic and make bot creation more difficult.
        - **Evasion:** Bots may try to **encrypt and manipulate network traffic** to hide their actions.
    - **Hardware Monitoring:**
        - **Hardware Fingerprinting:** Anti-cheat systems can **create a "fingerprint" of the player’s hardware** to detect if the same computer is being used on multiple accounts, a common sign of bot usage.
        - **Hardware Blocking:** Some systems, like PunkBuster, can permanently block access to a game from specific hardware.
- **Anti-Cheat Evasion Techniques:** Bot developers use various techniques to avoid detection, including:
    
    - **Code Obfuscation:**
        - **Complicating Analysis:** Code obfuscation involves **making the bot’s code difficult to understand and analyze**.
        - **Techniques:** Methods such as string encoding, adding junk code, encryption, and executable packing are used.
    - **Packing:**
        - **Compression and Encryption:** Packing **compresses and encrypts the bot’s executable**, making it more difficult to analyze. When executed, the packer decrypts the code in memory for execution.
        - **Tools:** Common packers include UPX, Armadillo, Themida, and ASPack.
    - **Anti-Debugging:**
        - **Evading Debuggers:** The bot implements **techniques to detect and avoid debugging** to hinder analysis of its code.
        - **Altered Behavior:** When a debugger is detected, the bot may alter its behavior, making analysis even more difficult.
    - **Use of Proxies:**
        - **Traffic Redirection:** Bots use proxies to **redirect their network traffic**, thereby hiding the user’s real IP address and making identification more difficult.
        - **Avoiding Blocks:** Proxies can help avoid IP blocks or access restrictions.
    - **Manipulation of Game Information:**
        - **Data Modification:** Bots attempt to **modify the information sent to the game server** so that it appears that the actions are performed by a legitimate player.
        - **Player Emulation:** Bots must also be capable of emulating legitimate player actions to avoid detection by behavioral analysis.
        - **Function Bypassing:** If the anti-cheat interferes with the functions used to modify memory, the bot should copy those functions to a new DLL and perform modifications in that copy.
        - **Keyboard Message Simulation:** The bot must use all keyboard messages (WM_KEYDOWN, WM_CHAR, WM_KEYUP) to simulate input effectively and avoid detection.
    - **Minimizing the Bot's Footprint:**
        - **Concealment:** Bots should **minimize their footprint** to avoid detection by using generic file and process names, and by hiding their interface.
        - **Random Names:** Using random file names and directories for the bot can help avoid detections based on specific names.
    - **Randomization of Actions:**
        - **Varying Patterns:** Bots **randomize their actions** to avoid repetitive patterns that might indicate bot usage.
        - **Human Behavior Simulation:** The goal is for the bot to simulate the behavior of a real player.
- **Evasion of Screenshot Capture:**
    
    - **Concealment:** Hide information on screen by using images or drawing the cheat graphics over the game screen.
    - **Alteration:** Hackers may try to alter the screenshots sent to the anti-cheat so that the cheats are not visible.
- **Reverse Engineering the Anti-Cheat:**
    
    - **System Analysis:** Cheat developers spend time analyzing the anti-cheat to understand how it works and to find vulnerabilities that can be exploited to bypass it.
- **Masquerading as a Legitimate Tool:** Some hackers may attempt to make their cheat or bot appear as a legitimate software application.
    
- **Practical Example (Evasion of Signature-Based Detection):**
    
    1. **Signature Analysis:** The bot developer analyzes the bot’s code and looks for code fragments that are detected by the anti-cheat.
    2. **Obfuscation:** The developer obfuscates the code, for example, by changing the order of instructions or encrypting parts of the code.
    3. **Testing:** The developer tests the bot to ensure that the obfuscation is effective and that it is no longer detected by the anti-cheat.
- **Tools for Anti-Cheat Evasion:**
    
    - **Debuggers (OllyDbg, x64dbg):** For analyzing the behavior of the game and the anti-cheat.
    - **Disassemblers (IDA Pro, Ghidra):** For examining the binary code of the game and the anti-cheat.
    - **Packers:** To compress and encrypt the bot’s executable (e.g., UPX, Armadillo, Themida, ASPack).
    - **Hooking Tools:** To intercept function calls.
    - **Obfuscation Tools:** To make code analysis more difficult.

## 9. Other Important Aspects

- **Networks:** It is useful to understand the OSI model to grasp how network communication works, although it is not necessary at the beginning.
- **Data Structures and Algorithms:** Having basic knowledge in these areas is useful for organizing and manipulating information.
- **Practice:** Learning these skills requires a lot of practice and experimentation.
- **Online Resources:** There are many forums, websites, videos, and books that can help you in your learning. Some recommendations are:
    - **UnknownCheats:** A forum with a wealth of information and hack code.
    - **GitHub:** It has many open-source projects to study.
    - **Books:** "Game Hacking" by Nick Cano and "Reversing Secrets" by Eldad Eilam are good options.
    - **C++ Learning Sites:** learncpp.com and the tutorials by The Cherno and The New Boston on YouTube.
    - **Telegram:** Gamehacking CLS &Programación.
    - **Guided Hacking:** It has a "bible" of game hacking and courses for beginners. (However, its platform is paid, the management is toxic, and all the information you need is available on Google, so this platform is not recommended.)

## 10. Recommendations

- **Start with simple games without anti-cheat** to practice the basic techniques.
- **Don’t be discouraged by failures;** it is a learning process that requires time and perseverance.
- **Participate in forums and communities** to learn from others and share your knowledge.
- **Always keep in mind the legal and ethical implications** of game hacking.

---

> Here I attach important resources that I believe will help us in our learning process.


# Learning Resources
## GitHub
- [The Ultimate Game Hacking Resource](https://github.com/dsasmblr/game-hacking/)
- [The Ultimate Online Game Hacking Resource](https://github.com/dsasmblr/hacking-online-games/)
- [Topic: Game Bot](https://github.com/topics/game-bot?l=python&o=desc&s=stars)
- [Gaming using Computer Vision](https://github.com/paulonteri/play-game-with-computer-vision#gaming-using-computer-vision)
- [GameHacking.gg](https://github.com/jhllc/Unity-Game#gamehackinggg)
- [CTF Game Challenges](https://github.com/mrT4ntr4/CTF-Game-Challenges#ctf-game-challenges)
- [Game Hacking Academy](https://gamehacking.academy/)

## YouTube
- [loab](https://www.youtube.com/@loabical/videos)
- [DeadOverflow](https://www.youtube.com/@deadoverflow/videos)
- [Low Level](https://www.youtube.com/@LowLevelTV/videos)
- [GynvaelEN](https://www.youtube.com/@GynvaelEN)
- [aXXo](https://www.youtube.com/@axxo1337)
- [Baseult Private](https://www.youtube.com/@baseultprivate9137)
- [Apxaey](https://www.youtube.com/@apxaey1459)
- [iwanMods](https://www.youtube.com/@iwanMods)
- [Dex](https://www.youtube.com/@DexTag)
- [Cyborg Elf](https://www.youtube.com/@CyborgElf/videos)
- [Hack In The Box Security Conference](https://www.youtube.com/@hitbsecconf/videos)
- [OWASP DevSlop](https://www.youtube.com/@OWASPDevSlop)
- [247CTF](https://www.youtube.com/@247CTF)
- [The Cyber Mentor](https://www.youtube.com/@TCMSecurityAcademy)
- [XorEAX MrGamer](https://www.youtube.com/@xoreaxmrgamer/videos)
- [The Gsm Work](https://www.youtube.com/@TheGsmWork/videos)
- [Alan Levy](https://www.youtube.com/@soy-elmago/videos)
- [John Hammond](https://www.youtube.com/@_JohnHammond)
- [WiseCereal](https://www.youtube.com/@WiseCereal/videos)
- [Game Jacker](https://www.youtube.com/@GameJacker/videos)
- [cazz](https://www.youtube.com/@cazz)
- [EddyoT&G](https://www.youtube.com/@EddyoTutos/videos)
- [LiveOverflow](https://www.youtube.com/@LiveOverflow/videos)
- [Classic Game Hacking](https://www.youtube.com/@ClassicGameHacking/videos)
- [swedz c#](https://www.youtube.com/@SwedishTwat/videos)
- [Intigriti](https://www.youtube.com/@intigriti)
- [Kian Brose](https://www.youtube.com/@KianBrose/videos)
- [Null](https://www.youtube.com/@null7953/videos)
- [Guided Hacking](https://www.youtube.com/@GuidedHacking)
- [Cheat The Game](https://www.youtube.com/@ChrisFayte)
- [Stephen Chapman](https://www.youtube.com/@StephenChapman/videos)
- [CursoReversing](https://www.youtube.com/@cursoreversing1952)



---

# NotebookLM-Indexed Resources

- [GAME HACKING 1 – ANTI CHEAT BYPASS](https://pt.linkedin.com/posts/joas-antonio-dos-santos_game-hacking-1-anti-cheat-bypass-activity-6977431747588206592-Jp7V)
- [Game Hacking: Developing Autonomous Bots for Online Games](https://www.amazon.com/-/es/Game-Hacking-Developing-Autonomous-Online/dp/1593276699/ref=sr_1_1?__mk_es_US=%C3%85M%C3%85%C5%BD%C3%95%C3%91&s=books&sr=1-1)
- [Practical Video Game Bots: Automating Game Processes using C++, Python, and AutoIt](https://www.amazon.com/-/es/Ilya-Shpigor-ebook/dp/B07GRM2G5Q/ref=sr_1_1?__mk_es_US=%C3%85M%C3%85%C5%BD%C3%95%C3%91&s=books&sr=1-1)
- [Ghidra Software Reverse-Engineering for Beginners: Master the art of debugging, from understanding code to mitigating threats](https://www.amazon.com/-/es/Ghidra-Software-Reverse-Engineering-Beginners-understanding/dp/B0DJGQ91R5/ref=sr_1_1?__mk_es_US=%C3%85M%C3%85%C5%BD%C3%95%C3%91&s=books&sr=1-1)
- [Malware and Reverse Engineering Complete Collection by Joas](https://elhacker.info/ebooks%20Joas/Malware%20and%20Reverse%20Engineering%20Complete%20Collection%20by%20Joas.pdf)
- [Malware Analysis and Detection Engineering: A Comprehensive Approach to Detect and Analyze Modern Malware](https://www.amazon.com/-/es/Malware-Analysis-Detection-Engineering-Comprehensive/dp/1484261925/ref=sr_1_1?__mk_es_US=%C3%85M%C3%85%C5%BD%C3%95%C3%91&s=books&sr=1-1)
- [Mastering Malware Analysis: A malware analyst's practical guide to combating malicious software, APT, cybercrime, and IoT attacks , Second Edition](https://www.packtpub.com/en-cy/product/mastering-malware-analysis-9781803240244)
- [Mastering Reverse Engineering: Re-engineer your ethical hacking skills](https://www.packtpub.com/en-cy/product/mastering-reverse-engineering-9781788835299)
- [HOW TO START GAME HACKING](https://www.youtube.com/watch?v=yW_ZxqVDLVE&list=TLGGu1ufcUE521AzMTAxMjAyNQ)
- [Game Hacking Explained in 8 Minutes (And How to Protect Your Games)](https://www.youtube.com/watch?v=uBxGUcsQf-w)
- [How to LEARN HACKING](https://www.youtube.com/watch?v=3_VfW6bDBdE)
- [Learn Reverse Engineering (for hacking games)](https://www.youtube.com/watch?v=0_Eif2qGK7I)
