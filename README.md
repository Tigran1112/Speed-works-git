# Speed Works Git

**Speed Works Git** is a simple script designed to help you save time while working with Git by automating some of the common commands.

## Installation

To install, just follow these steps:

1. Open your terminal.
2. Navigate to your home directory.
3. Edit the `.bashrc` or `.zshrc` file (depending on your shell) by adding the following function at the end of the file:

    ```bash
    swg() {
        com=$1
        two=$2
        three=$3

        if [ "$com" = "first" ]; then
            git init
            git add .
            git commit -m 0.1

            if [ -n "$two" ]; then
                git remote add origin "$two"
                git push origin master
            else
                echo "URL not provided."
            fi
        elif [ "$com" = "last" ] && [ -n "$two" ]; then
            git add .
            git commit -m "$two"
            git push origin master
        elif [ "$com" = "conf" ] && [ -n "$two" ] && [ -n "$three" ]; then
            git config --global user.name "$two"
            git config --global user.email "$three"
        else
            echo "Command not recognized or incorrect arguments."
        fi
    }
    ```

4. Save and close the file.
5. Run the following command to apply the changes:

    ```bash
    source ~/.bashrc
    ```

    or, for Zsh:

    ```bash
    source ~/.zshrc
    ```

## Usage

You can now use the `swg` command to simplify your Git workflow. Below are the available commands:

### 1. Initialize a Git repository and push to remote:

   ```bash
   swg first [repository-url]
  ```
  > commit name is 0.1
### 2. Simple push to remote:

   ```bash
   swg last [commit-name]
  ```
### 3. Set global config

   ```bash
   swg conf [your-username] [your-email]
  ```
Now, you're ready to use Speed Works Git! Simply type any of the following shortcuts to speed up your Git workflow.

> ⚡ **Speed up your Git workflow and save precious time!**

---

Made with ❤️ by Tigran
