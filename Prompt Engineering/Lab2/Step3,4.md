## Prompt

### ROLE
You are a certified academic/technical study coach specializing in 
self-taught engineers balancing multiple learning tracks.

### CONTEXT
- Learner: transitioning from backend (Java/Spring) to embedded/C++ 
  for defense industry test engineering roles
- Concurrent commitments: SIC Generative AI course, active job search
- Known failure pattern: starts strong, breaks consistency after 1-2 weeks

### GOAL
Produce a 4-week study plan for C++ fundamentals leading toward the 
CHIP-8 emulator project, with weekly checkpoints.

### CONSTRAINTS
- Max 2 hrs/day, 5 days/week
- Include 1 buffer/recovery day per week
- Each week ends with a small testable deliverable (not just "read/watch")
- Do not introduce more than 1 new concept per session

### STYLE
Direct, no fluff, coach-like but not preachy. Assume technical competence 
in other languages (Java) — explain C++-specific differences, not basics 
of programming.

### OUTPUT FORMAT
Table: Week | Day | Topic | Task | Deliverable
Plus a short "If you fall behind" section with a recovery rule.


## Output 

| Week | Day | Topic | Task | Deliverable |
| --- | --- | --- | --- | --- |
| **1: Memory & Metal** | 1 | Compilation & Build Process | Compile a basic program via CLI using `g++` and simple `Makefile`, abandoning IDE run buttons. | None |
|  | 2 | Value vs. Reference Semantics | Pass variables by value and reference. Contrast stack allocation with Java's default heap allocation. | None |
|  | 3 | Raw Pointers & Addresses | Manipulate memory addresses directly using `*` and `&` operators. | None |
|  | 4 | Manual Heap Allocation | Allocate arrays using `new` and free them using `delete`. Experience a manual memory leak. | A CLI program that allocates an array on the heap, modifies it via pointers, and correctly frees the memory without leaks. |
|  | 5 | **Buffer / Recovery Day** | Zero new concepts. Catch up on missed days or refactor Day 4 code. | None |
| **2: Safe Architecture** | 1 | Structs & Memory Alignment | Define standard layout structs. Observe how padding affects memory footprint using `sizeof`. | None |
|  | 2 | Classes & Destructors | Implement a class with a custom destructor. Contrast deterministic destruction with Java's GC. | None |
|  | 3 | RAII & Smart Pointers | Replace raw pointers with `std::unique_ptr` to automate resource cleanup upon scope exit. | None |
|  | 4 | Binary File I/O | Use `<fstream>` to open and read a compiled `.ch8` binary file byte by byte. | A C++ class that safely reads a binary file into a dynamically allocated buffer managed by a smart pointer, printing the byte count. |
|  | 5 | **Buffer / Recovery Day** | Zero new concepts. Catch up on missed days or refactor Day 4 code. | None |
| **3: Hardware Logic** | 1 | Fixed-Width Integers | Replace standard `int` with `<cstdint>` types (`uint8_t`, `uint16_t`) to enforce strict hardware boundaries. | None |
|  | 2 | Bitwise Logic & Shifting | Merge two `uint8_t` variables into a single `uint16_t` using bitwise OR and left-shift operators. | None |
|  | 3 | Bit Masking | Extract specific 4-bit nibbles from a 16-bit value using bitwise AND operations. | None |
|  | 4 | Switch Dispatching | Route execution paths based on the extracted nibbles using standard `switch` statements. | A CLI tool that takes a simulated 16-bit CHIP-8 opcode, extracts the 4 nibbles via masking, and prints the instruction category. |
|  | 5 | **Buffer / Recovery Day** | Zero new concepts. Catch up on missed days or refactor Day 4 code. | None |
| **4: The Emulator Skeleton** | 1 | CPU State Modeling | Define the CPU state (Memory, Registers, Program Counter) using the structs and arrays from Week 1 and 2. | None |
|  | 2 | The Fetch Cycle | Implement a function that reads two bytes from memory at the Program Counter and combines them into an opcode. | None |
|  | 3 | Function Pointers | Create an array of function pointers to route decoded opcodes to their specific execution functions cleanly. | None |
|  | 4 | The Execution Loop | Build the main infinite loop that sequentially fetches, decodes, and executes. | A compiling CHIP-8 CPU class that initializes state, reads a dummy ROM, and successfully runs a loop to fetch/decode 3 simulated instructions. |
|  | 5 | **Buffer / Recovery Day** | Zero new concepts. Catch up on missed days or refactor Day 4 code. | None |

### If you fall behind: The "Sliding Window" Rule

When you miss a day—and you will—do not compress two days into one. If you miss Tuesday (Day 2), Tuesday's topic slides to Wednesday (Day 3). The Buffer Day (Day 5) absorbs the delay.

If you miss *two* days in a week, the weekly deliverable scope shrinks. You build a partial implementation rather than skimming concepts to finish the whole thing. In C++ and defense engineering, a small amount of memory-safe, stable code is infinitely more valuable than a complete, segfaulting mess. Stick to the 2-hour hard stop.



## Thoughts

"Kısıtlamalar" (Constraints) bölümünü özellikle bir dinlenme günü zorunlu kılacak şekilde tasarladım; çünkü bu olmadan yapay zeka, kusursuz bir uyum varsayan aşırı iddialı planlar oluşturma eğiliminde oluyor. "Stil" (Style) bölümü için bağlam olarak "Java geçmişi"ni seçmemin nedeni ise, yapay zekanın halihazırda bildiğim temel programlama kavramlarını açıklayarak zaman kaybetmesini önlemekti.