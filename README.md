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

```
