# My 42 Get Next Line

## Description

**Get Next Line** is a function implemented as part of the 42 School curriculum to simplify reading lines from a file descriptor. Unlike standard methods, this function reads a file one line at a time, making it especially useful for parsing input streams. The function supports any file descriptor, including files and standard input, and is designed to handle varying buffer sizes efficiently.

Key features:
- Returns a single line from a file descriptor, including the trailing newline character if present.
- Handles multiple calls to read lines sequentially until the end of the file is reached.
- Includes the use of static variables to preserve state across function calls for continuous line reading.

This project focuses on deepening understanding of file I/O, memory management, and static variables in C.

---

## Installation

Clone the repository:

```
git clone https://github.com/your-account/get_next_line.git
```

Compile the project with a specified buffer size:

```
cc -Wall -Wextra -Werror -D BUFFER_SIZE=42 get_next_line.c get_next_line_utils.c
```

Replace `BUFFER_SIZE=42` with the desired buffer size.

---

## Usage

Include the `get_next_line.h` header in your project:

```c
#include "get_next_line.h"

int main(void)
{
    int fd = open("example.txt", O_RDONLY);
    char *line;

    while ((line = get_next_line(fd)))
    {
        printf("%s", line);
        free(line);
    }
    close(fd);
    return 0;
}
```

Compile the program and run it with a text file:

```
./a.out
```

Example output for a file containing:
```
Hello,
World!
```

Will print:
```
Hello,
World!
```
