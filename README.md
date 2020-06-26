# fairport

## Install

```
sudo cp fairport /usr/share/fairport
sudo sysctl -w kernel.core_pattern="|/usr/share/fairport %p %s %c %d %P"
```

## To test

```
# create a program that crashes
echo "int main() { int *ptr = 0; *ptr = 1; }" | gcc -o crasher -x c -

# enable core-dumps
ulimit -c unlimited
mkdir -p ~/cores
./crasher

ls ~/cores/
```
