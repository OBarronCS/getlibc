# getlibc

A shell script to pull the `libc` and `ld-linux` loader file from a Docker image. Useful for pwn.

It detects the use of a [redpwn jail](https://github.com/redpwn/jail) container and grabs the correct libc (the one that applies to the challenge file in /srv).

# Install
```sh
git clone https://github.com/OBarronCS/getlibc.git ~/getlibc
```

#### bash
```sh
echo 'export PATH="$HOME/getlibc/bin:$PATH"' >> ~/.bashrc
```
#### zsh
```sh
echo 'export PATH="$HOME/getlibc/bin:$PATH"' >> ~/.zshrc
```


# Usage
Running `getlibc` will grab the `libc` and the dynamic loader from the container and place them in the current directory. If the file names already exist, it will not overwrite them.

With no arguments, it looks for a `Dockerfile` in the current directory. Otherwise, you can specify the path or the Docker image name.
```sh
getlibc [-f Dockerfile_path] [--image Image_name]
```