# Assignment One


## 1.Make a directory called LC in your home dir
```sh
$ cd ~
$ mkdir LC
```

## 2. Use touch to create a new file called test in your LC dir.
```sh
$ cd LC
$ touch test
```

## 3. Write the following into that file
```sh
$ vim test
```
 Write

Then click esc and write :wq to quit vim.

## 4. Try to execute the file, i.e. type the path to the script (./test) into your shell and press enter. Understand why it doesn’t work by consulting the output of ls (hint: look at the permission bits of the file). is it executable ?

It is not executable. As it is rw- only for the owner. And we need to be able to execute this file.




## 5. Run the command by explicitly starting the sh interpreter, and giving it the file test as the first argument, i.e. sh test. Why does this work, while ./test didn’t?
Because sh test only needs the reading permission. While ./test need to be able to execute the file (Needs exeuction permission).

## 7. Use chmod to make it possible to run the command ./test rather than having to type sh test. How does your shell know that the file is supposed to be interpreted using sh?
```sh
$ chmod u+x ./test
```
This way, we added the execution permission.
Or 
```sh
$ chmod 744 ./test
```
So the pemission will be rwxr--r-- for the test file.

It knows that it is supposed to be interpreted using sh becuase of the first line in our srcipt which determine the language of the script.

## 8. Make a python file called testpy , in the same manner make the file print "hello world" when executing it ./testpy

```sh
$ touch testpy
$ vim testpy 
```
Type print("Hello World") in the file.
```sh
$ chmod u+x ./testpy
$ ./testpy
```


## 9. What is the diiference between > and >> explain with exapmles

>Overwrite the file, while >> append to the file.
Ls > t .. will store the output of ls command in t 
But, when we execute it again with any other command, it will remove the content of t and replace it by the new one. 
However, if we used >> it will append the new command’s output to the original content of the file.
//Note that ’t’ is a text file.



## 10. We talked about aliases. it is very common to alias ll to ls -alh How can you do it ?

```sh
$ echo "alias ll='ls-alh'" >> ~/.bashrc
$ exec bash
$ ll
```




## Mohamed Khalid Almarsafy