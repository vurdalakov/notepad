# Useful bash tricks

####  Set a variable to the command output

```
OUTPUT="$(ls -1)"
echo "${OUTPUT}"
```

#### Increment a variable

```
((var++))
```

#### Delete directory only if it exists

```
logdir=/tmp/logs
if [-d "$logdir"]; then rm -rf "$logdir"; fi
```

#### Replace space with new line

```
echo /dev/sd? | tr " " "\n"
```
