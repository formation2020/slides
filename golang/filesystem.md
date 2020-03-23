# Filesystem
{id: filesystem}


## os.stat information about a file or directory (file exists)
{id: os-stat}
{i: os}
{i: IsNotExist}
{i: Stat}

![](examples/file-stat/stat.go)

```
Error: stat hello/world: no such file or directory
```

If the directory where the file can be found is not executable by the user who runs this code, we'll get
the following error:

```
Error: stat hello/world: permission denied
```

## List Directory 
{id: list-directory}
{i: ioutil}
{i: ReadDir}

![](examples/list_directory/listdir.go)
