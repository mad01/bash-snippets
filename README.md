# bash-snippets


#### functions
```shell
checkBinary() {
    if ! which $1 >&/dev/null; then
        echo "Unable to locate $1, please ensure it is installed and on your \$PATH."
        exit 1
    fi
}

checkBinary brew
```

```shell
function buildTestContainer() {
	docker build -t golang-template-repo:latest - <<EOF
FROM golang:1.11.1
RUN apt update -y \ 
    && apt install -y \
       locales \
       wget \
       make \
       git \
    && localedef -i en_US -c -f UTF-8 -A /usr/share/locale/locale.alias en_US.UTF-8
EOF
}
```

color
```shell
RESTORE=$(echo -en '\033[0m')
RED=$(echo -en '\033[00;31m')
GREEN=$(echo -en '\033[00;32m')
YELLOW=$(echo -en '\033[00;33m')
BLUE=$(echo -en '\033[00;34m')
MAGENTA=$(echo -en '\033[00;35m')
PURPLE=$(echo -en '\033[00;35m')
CYAN=$(echo -en '\033[00;36m')
LIGHTGRAY=$(echo -en '\033[00;37m')
LRED=$(echo -en '\033[01;31m')
LGREEN=$(echo -en '\033[01;32m')
LYELLOW=$(echo -en '\033[01;33m')
LBLUE=$(echo -en '\033[01;34m')
LMAGENTA=$(echo -en '\033[01;35m')
LPURPLE=$(echo -en '\033[01;35m')
LCYAN=$(echo -en '\033[01;36m')
WHITE=$(echo -en '\033[01;37m')

# Test
echo ${RED}RED${GREEN}GREEN${YELLOW}YELLOW${BLUE}BLUE${PURPLE}PURPLE${CYAN}CYAN${WHITE}WHITE${RESTORE}

```

Check if array is empty
```shell
if [ ${#errors[@]} -eq 0 ]; then
    echo "No errors, hooray"
else
    echo "Oops, something went wrong..."
fi
```
