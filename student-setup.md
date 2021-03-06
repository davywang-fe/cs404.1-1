Student Setup
-------------
Normally, repositories house code that all developers use as a base to build their changes off of.
When other developers make changes, all developers pull them in and continue their work on top.
In our case, however, each student will have a separate fork of this repository in order to complete
their assignments. Furthermore, each student must keep their fork private so as to prevent any
possible plagiarism. Unfortunately, GitHub does not allow private forks of public repositories.

For this reason, we won't be using the standard GitHub workflow here. Instead, we have to jump
through some hoops in order to support our specific use case, while also using GitHub's repository
hosting platform.

Part 1: Operating System Specific Setup
---------------------------------------
Use the following instructions to properly set up your environment and your repository. The
instructions are slightly different for different operating systems.

### Mac OS X
Mac OS X doesn't come standard with a lot of the developer tools necessary for this course. To get
these developer tools, you will have to install XCode tools on your computer. To do so, follow the
instructions below:

- Install XCode Tools
  - In a terminal, run the command `xcode-select --install`
- Install Bazel (via [homebrew](https://brew.sh))
  - In a terminal window, run the following commands:
    ```
    /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
    brew tap bazelbuild/tap
    brew install bazelbuild/tap/bazel
    ```

### Windows
Windows doesn't come standard with a lot of the developer tools necessary for this course. To get
these developer tools, you will have to install a few different programs. To do so, follow the
instructions below:

- [Download](https://git-scm.com/download/win) and install `git`
  - The default settings already selected during installation are fine to use
- Install Bazel
  - In a new PowerShell window, execute the following commands:
    ```
    Set-ExecutionPolicy RemoteSigned -scope CurrentUser
    iwr -useb get.scoop.sh | iex
    scoop install bazel
    ```

Part 2: Bootstrap Your Repository
---------------------------------
Use the following instructions to properly set up your environment and your repository.

- Ensure you have a GitHub account, have verified your email address, and are signed in
- [Create a new repository](https://github.com/new) on GitHub
  - Name your repository `cs404.1`
  - Ensure the repository is marked private
  - Create the repository
- Add `fsareshwala` as a collaborator
  - Visit the `Settings` tab
  - Select the `Manage access` section on the left
  - Click `Invite a collaborator` near the bottom of the page
  - Add the `fsareshwala` user as a collaborator to your repository
- Bootstrap your repository
  - Execute the following command in a new terminal
  - **Note**: make sure to replace `username` in the command below with your GitHub username
  ```
  curl https://raw.githubusercontent.com/fsareshwala/dotfiles/master/prefix/bin/bootstrap | bash -s cs404.1 username

  ```
  - You will now have a directory named `cs404.1` where you executed the command above. This is your
    assignment directory where you will do your work.

Part 3: Installing an IDE
-------------------------
An integrated development environment (IDE) is a tool that developers use to work on code. The IDE
includes all of the elements necessary to compile, run, and debug our programs. The IDE we will use
for this class is IntelliJ IDEA.

**Note**: you are not required to use IntelliJ IDEA or even an IDE. You may use whatever tools you
prefer using. However, IntelliJ IDEA is the supported IDE for this class. If you venture off on your
own, you will be responsible for ensuring your environment works and runs programs properly. It is
up to you to determine whichever development environment works best for your personal tastes. As
such, detailed instructions on how to perform various environment related operations won't be
provided. I assume that by this stage of your software engineering career, you are familiar with
your tools of choice.

Follow the instructions below to install and properly set up your IDE.

- [Download](https://www.jetbrains.com/idea/download) and install IntelliJ IDEA
- Open IntelliJ IDEA and open the preferences pane
- Search for and install the following extensions within IntelliJ IDEA
  - `Bazel` by Google
  - `google-java-format` by Google`
- Restart IntelliJ IDEA after installing your plugins
- Load your assignment repository by importing a Bazel project in IntelliJ IDEA
- Click through until the repository is loaded (default settings are fine to use)

Part 4: Making Your First Commit
--------------------------------
Now that you have properly configured your system, let's start making some changes.

- Identify yourself within your repository
  - Open the `name.md` file in the top level root of the repository
  - Replace the contents with your name
  - Commit the addition and push the change to GitHub
  - This is how I know who the repository belongs to
