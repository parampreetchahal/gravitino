<!--
  Licensed to the Apache Software Foundation (ASF) under one
  or more contributor license agreements.  See the NOTICE file
  distributed with this work for additional information
  regarding copyright ownership.  The ASF licenses this file
  to you under the Apache License, Version 2.0 (the
  "License"); you may not use this file except in compliance
  with the License.  You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

  Unless required by applicable law or agreed to in writing,
  software distributed under the License is distributed on an
  "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY
  KIND, either express or implied.  See the License for the
  specific language governing permissions and limitations
  under the License.
-->

# Contributing to Apache Gravitino

Thank you for your interest in contributing to Apache Gravitino! Your support is invaluable in enhancing the project, and we warmly welcome contributions of all kinds. Gravitino appreciates your assistance in making it better, whether through code contributions, documentation, tests, best practices, graphic design, or any other means that have a positive impact.

To ensure a smooth and productive collaboration, please take a moment to review and follow our contribution guidelines before getting started.

## Table of contents

- [Getting Started](#getting-started)
  - [Fork the Repository](#fork-the-repository)
  - [Development Setup](#development-setup)
  - [Using IntelliJ (Optional)](#using-intellij-optional)
  - [Using VS Code (Optional)](#using-vs-code-optional)
  - [Handling Memory Issues in WSL](#handling-memory-issues-in-wsl)
- [Project Overview and Policies](#project-overview-and-policies)
  - [Project Overview](#project-overview)
  - [Management Policies](#management-policies)
  - [Future Development Directions](#future-development-directions)
- [Contribution Guidelines](#contribution-guidelines)
  - [Code of Conduct](#code-of-conduct)
  - [Reporting Bugs](#reporting-bugs)
  - [Suggesting Enhancements](#suggesting-enhancements)
  - [Good First Issues](#good-first-issues)
  - [Working on Issues](#working-on-issues)
  - [Creating Pull Requests](#creating-pull-requests)
  - [The Review Process](#the-review-process)
- [Testing](#testing)
- [Coding Standards](#coding-standards)
- [Community and Communication](#community-and-communication)
- [License](#license)

## Getting started

### Fork the repository

Either click the "Fork" button at the top right of the repository's page on GitHub OR create a fork on your local machine using `git clone`.

```bash
git clone https://github.com/apache/gravitino.git
cd gravitino
```

### Development Setup

Once you have cloned the [GitHub repository](https://github.com/apache/gravitino), see [how to build](/docs/how-to-build.md) for instructions on how to build, or you can use the provided docker images at [Apache DockerHub repository](https://hub.docker.com/u/apache).

To stop and start a local Gravitino server via `bin/gravitino.sh start` and `bin/gravitino.sh stop` in a Gravitino distribution, see [how to build](/docs/how-to-build.md) for more instructions.

### Using IntelliJ (Optional)

**On Windows:**

1. Open the Gravitino project that was just downloaded.

2. Go to `File > Project Structure > Project` and change to the SDK you downloaded in WSL.

3. If the SDK does not appear, manually add the SDK.

4. To find the SDK location, run this command in WSL:

    **On Ubuntu (WSL):**
    ```sh
    which java
    ```

IntelliJ IDEA is an integrated development environment (IDE) for Java development. Setting the project SDK ensures that IntelliJ uses the correct Java version to build and run the project.

You can open up WSL in the IntelliJ terminal. Find the down arrow and select ubuntu.

### Using VS Code (Optional)

#### Set up WSL Extension in VSCode

**On Windows:**

1. Open VSCode extension marketplace, search for and install **WSL**.

2. Press `Ctrl+Shift+P` to open the command palette, and run `Shell Command: Install 'code' command in PATH`.

Installing the WSL extension in VSCode allows you to open and edit files in your WSL environment directly from VSCode. Adding the `code` command to your PATH lets you open VSCode from the WSL terminal.

#### Verify and Configure Environment Variables

**On Windows:**

1. Add VSCode path to the environment variables. The default installation path for VSCode is usually:

    ```plaintext
    C:\Users\<Your-Username>\AppData\Local\Programs\Microsoft VS Code\bin
    ```

    Replace `<Your-Username>` with your actual Windows username.

    Example:

    ```plaintext
    C:\Users\epic\AppData\Local\Programs\Microsoft VS Code\bin
    ```

Adding VSCode to the environment variables ensures you can open VSCode from any command prompt or terminal window.

**On Ubuntu (WSL):**

```sh
code --version
cd gravitino
code .
```

Running `code --version` verifies that the `code` command is available. Using `code .` opens the current directory in VSCode.

#### Open a WSL Project in Windows VSCode

**On Ubuntu (WSL):**

1. **Navigate to Your Project Directory**

   Use the terminal to navigate to the directory of your project. For example:

   ```sh
   cd gravitino
   ```

2. **Open the Project in VSCode**

   In the WSL terminal, type the following command to open the current directory in VSCode:

   ```sh
   code .
   ```

  This command will open the current WSL directory in VSCode. If you haven't added `code` to your path, follow these steps:

- Open VSCode on Windows.

- Press `Ctrl+Shift+P` to open the command palette.

- Type and select `Shell Command: Install 'code' command in PATH`.

3. **Ensure Remote - WSL is Active**

   When VSCode opens, you should see a green bottom-left corner indicating that VSCode is connected to WSL. If not, click on the green area and select `Remote-WSL: New Window` or `Remote-WSL: Reopen Folder in WSL`.

4. **Edit and Develop Your Project**

   You can now edit and develop your project files in VSCode as if they were local files. The Remote - WSL extension seamlessly bridges the file system between Windows and WSL.

### Handling Memory Issues in WSL

Here are some solutions if you encounter a memory issue when using WSL.

1. **Shut down WSL**  
   If your WSL is open, you can shut it down in Windows PowerShell using the following command:  

   ```powershell
   wsl --shutdown
   ```

2. **Navigate to user folder**  

   Open File Explorer and navigate to `C:\Users\<your-username>`.

3. **Create the `.wslconfig` file**  

   Open up Notepad or another text editor and input the following:  

   ```plaintext
   [wsl2]
   memory=4GB   # Limits VM memory in WSL 2 up to 4GB
   processors=4 # Makes the WSL 2 VM use four virtual processors
   ```

   *The memory and processor usage can be changed depending on your system's hardware.*

4. **Save the file**  

   Save the file as `".wslconfig"`. Be sure to include the quotes to let Windows know that this isn't a text file.

## Project Overview and Policies

### Project Overview

For an overview of the project, see [README.md](README.md).

### Management Policies

For project management policies, refer to [GOVERNANCE.md](GOVERNANCE.md).

### Future Development Directions

Refer to the [ROADMAP.md](ROADMAP.md) document for future development directions.

## Contribution guidelines

### Code of Conduct

Please read and follow the [Code of Conduct](CODE_OF_CONDUCT.md). Gravitino provides a welcoming and inclusive environment for all contributors.

### Reporting bugs

If you find a bug in Gravitino, please open an issue on GitHub. Include as much detail as possible, such as a clear description, reproduction steps, and your environment. Please follow the template provided. If you encounter a security issue, please refer to [SECURITY.md](SECURITY.md).

### Suggesting enhancements

If you have ideas for enhancements or new features, feel free to create an issue to discuss them. Gravitino welcomes suggestions and provides prompt feedback on their feasibility and relevance.

### Good First Issues

If you are new to open source or can't find something to work on, check out the [Good First Issues list](https://github.com/apache/gravitino/contribute).

### Working on Issues

Check out the list of open issues and find one that interests you. You can also comment on an issue to indicate that you're working on it. Please keep the issue updated with your progress.

## Creating Pull Requests

Create a new branch from `main` for your changes:

```bash
git checkout -b your-branch-name
```

Make your changes and commit them. Be sure to write clear and concise commit messages.

```bash
git commit -m "Your commit message"
```

Push your changes to your fork on GitHub:

```bash
git push your-branch-name
```

After you have pushed your changes, create a pull request (PR) in the Gravitino repository. Be sure to provide a detailed description of your changes, reference any related issues, and please follow the template provided. Gravitino's maintainers evaluate pull requests, offer feedback, and assist in merging project changes.

### The Review Process

For details on the review process, please refer to [MAINTAINERS.md](MAINTAINERS.md).

## Testing

The CI infrastructure runs unit and integration tests on each pull request. Please make sure these tests pass before making a pull request.

The unit tests run on every build, and integration tests run as needed. See [how to test](docs/how-to-test.md) for more information.

Add unit tests to provide coverage when adding new code or fixing a bug.

## Coding standards

Spotless checks code formatting. If your code is correctly formatted, the build succeeds. To format your code correctly, please use Spotless.

```bash
./gradlew spotlessApply
```

All files must have a license header, and the build fails if any files are missing license headers. If you are adding third-party code, you may need to add the third-party license to Gravitino's LICENSE and NOTICE files. If you are unsure of how to do this, please ask for help.

Please add unit tests to provide code coverage for any bugs or new code. The project may not accept code without unit tests.

All text files should use macOS/unix style line endings (LF), not Windows-style line endings (CRLF).

## Community and communication

Join the [community mailing list](https://lists.apache.org/list.html?dev@gravitino.apache.org) to discuss ideas and seek help. You are also encouraged to use GitHub discussions.

## License

When contributing to this project, you agree that your contributions use the Apache License version 2. Please ensure you have permission to do this if your employer requires it.

Thank you for your contributions to Gravitino! The project appreciates your help in making it a success.
