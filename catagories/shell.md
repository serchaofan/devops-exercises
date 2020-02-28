# Shell Scripting

<a name="shell-scripting-beginner"></a>

<details>
<summary>Tell me about your experience with shell scripting</summary><br><b>

</b></details>

<details>
<summary>What this line in scripts mean?: <code>#!/bin/bash</code></summary><br><b>

`#!/bin/bash` is She-bang

/bin/bash is the most common shell used as default shell for user login of the linux system. The shell’s name is an acronym for Bourne-again shell. Bash can execute the vast majority of scripts and thus is widely used because it has more features, is well developed and better syntax.

</b></details>

<details>
<summary>What do you tend to include in every script you write?</summary><br><b>

Few example:

- Comments on how to run it and/or what it does
- Adding "set -e" since I want the script to exit if a certain command failed

You can have an entirely different answer. It's based only on your experience.
</b></details>

<details>
<summary>True or False?: when a certain command/line fails, the script, by default, will exit and will no keep running</summary><br><b>

Depends on the language and settings used.
When a script written in Bash fails to run a certain command it will keep running and will execute all other commands mentioned after the command which failed.
Most of the time we would actually want the opposite to happen. In order to make Bash exist when a specific command fails, use 'set -e' in your script.
</b></details>

<details>
<summary>Today we have tools and technologies like Ansible. Why would someone still use shell scripting?</summary><br><b>

- Speed
- The module we need doesn't exist
- We are delivering the scripts to customers who don't have access to the public network and don't necessarily have Ansible installed on their systems.
  </b></details>

<details>
<summary>Explain what would be the result of each command:

- <code>echo \$0</code>
- <code>echo \$?</code>
- <code>echo \$\$</code>
- <code>echo \$@</code>
- <code>echo \$#</code></summary><br><b>
  </b></details>

<details>
<summary>How do you debug shell scripts?</summary><br><b>

Answer depends on the language you are using for writing your scripts. If Bash is used for example then:

- Adding -x to the script I'm running in Bash
- Old good way of adding echo statements

If Python, then using pdb is very useful.
</b></details>

<details>
<summary>How do you get input from the user in shell scripts?</summary><br><b>

Using the keyword <code>read</code> so for example <code>read x</code> will wait for user input and will store it in the variable x.
</b></details>

<details>
<summary>Explain conditionals and how do you use them</summary><br><b>
</b></details>

<details>
<summary>What is a loop? What types of loops are you familiar with?</summary><br><b>
</b></details>

<details>
<summary>Explain <code>continue</code> and <code>break</code>. When do you use them if at all?</summary><br><b>
</b></details>

<details>
<summary>How to store the output of a command in a variable?</summary><br><b>
</b></details>

<details>
<summary>How do you check variable length?</summary><br><b>
</b></details>

<details>
<summary>What is the difference between single and double quotes?</summary><br><b>
</b></details>

<details>
<summary>Write a script which will list the differences between two directories</summary><br><b>
</b></details>

##### Practical

<details>
<summary>Write a script to determine whether a host is up or down</summary><br><b>

**EXAMPLE ONE**

```
#!/bin/bash
SERVERIP=<IP Address>
NOTIFYEMAIL=test@example.com

ping -c 3 $SERVERIP > /dev/null 2>&1
if [ $? -ne 0 ]
then
   # Use mailer here:
   mailx -s "Server $SERVERIP is down" -t "$NOTIFYEMAIL" < /dev/null
fi
```

</b></details>

<details>
<summary>Write a script to remove all the empty files in a given directory (also nested directories)</summary><br><b>

**EXAMPLE ONE**

```
#! /bin/bash
for x in *
do
    if [ -s $x ]
    then
        continue
    else
        rm -rf $x
    fi
done
```

</b></details>

<a name="shell-scripting-advanced"></a>

#### Advanced

<details>
<summary>Explain the following code:

<code>:(){ :|:& };:</code>

</summary><br><b>
</b></details>

<details>
<summary>Can you give an example to some Bash best practices?</summary><br><b>
</b></details>

<details>
<summary>What is the ternary operator? How do you use it in bash?</summary><br><b>

A short way of using if/else. An example:

[[ $a = 1 ]] && b="yes, equal" || b="nope"
</b></details>

<details>
<summary>What does the following code do and when would you use it?
	
<code>diff <(ls /tmp) <(ls /var/tmp)</code>

</summary><br>
It is called 'process substitution'. It provides a way to pass the output of a command to another command when using a pipe <code>|</code> is not possible. It can be used when a command does not support <code>STDIN</code> or you need the output of multiple commands. 
https://superuser.com/a/1060002/167769
</details>
