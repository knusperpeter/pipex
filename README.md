# 📊 Pipex
A program that simulates shell command pipelines and redirections, developed as part of the 42 school curriculum. This project implements Unix/Linux pipe mechanics and process management.

## ⚠️ Notice to 42 Students
This repository serves as a reference. Please:
- Understand the code before using it
- Don't copy without comprehension
- Use it to learn concepts, not to bypass learning
- Implement your own solution to truly grasp the mechanics

## 🎯 Project Overview
Pipex recreates shell pipeline behavior by executing commands and managing data flow between processes. It handles file redirections and inter-process communication using pipes.

### Shell Equivalent
```bash
# Pipex command:
./pipex file1 cmd1 cmd2 file2

# Shell equivalent:
< file1 cmd1 | cmd2 > file2
```

## ✨ Features

### Core Functionality
- Input/output file handling
- Command execution with arguments
- Pipe-based inter-process communication
- Process creation and management
- Error handling and reporting

### Bonus Features
- Multiple pipe support
- Here document implementation
- Extended command chain execution

## 🚀 Getting Started

### Prerequisites
- GCC compiler
- Make
- UNIX-based operating system

### Installation
```bash
# Clone the repository
git clone https://github.com/yourusername/pipex.git

# Navigate to project directory
cd pipex

# Compile the program
make
```

### Usage

#### Basic Operation
```bash
./pipex infile "command1" "command2" outfile
```

#### Examples
```bash
# Count lines in a file
./pipex infile "ls -l" "wc -l" outfile

# Count words containing 'a1'
./pipex infile "grep a1" "wc -w" outfile
```

#### Bonus Features

##### Multiple Pipes
```bash
# Format: ./pipex infile cmd1 cmd2 cmd3 ... cmdn outfile
./pipex infile "grep a1" "sort" "uniq -c" "wc -l" outfile
```

##### Here Document
```bash
# Format: ./pipex here_doc LIMITER cmd1 cmd2 outfile
./pipex here_doc END "grep a1" "wc -w" outfile
```

## 🔧 Technical Implementation

### Key Components
- Process creation using `fork()`
- Pipe communication
- File descriptor management
- Command parsing and execution
- Path resolution for commands
- Signal handling

### Error Handling
The program handles various error cases:
- File access permissions
- Invalid commands
- Memory allocation failures
- Pipe creation errors
- Fork failures

## 💻 Code Structure
```
pipex/
├── src/
│   ├── main.c
│   ├── process.c
│   ├── command.c
│   └── utils.c
├── include/
│   └── pipex.h
└── Makefile
```

## 🧪 Testing
```bash
# Test basic functionality
./pipex infile "ls" "wc -l" outfile

# Test error handling
./pipex nonexistent "ls" "wc" outfile

# Test bonus features
./pipex infile "grep test" "sort" "uniq" outfile
```

## 📝 Common Issues and Solutions
- Ensure proper file permissions
- Check command path accessibility
- Handle memory allocation carefully
- Close unused file descriptors
- Manage child processes properly

## 🤝 Contributing
Feel free to submit issues and enhancement requests.

## 📜 License
This project is open source and available under the [MIT License](LICENSE).

---
*Built with understanding of Unix process management* 🔄
