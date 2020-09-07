# Virtualization

<details>
<summary>Explain what is Virtualization</summary><br><b>
</b></details>

<details>
<summary>What is "time sharing"?</summary><br><b>

Even when using a system with one physical CPU, it's possible to allow multiple users to work on it and run programs. This is possible with time sharing where computing resources are shared in a way it seems to the user the system has multiple CPUs but in fact it's simply one CPU shared by applying multiprogramming and multi-tasking.
</b></details>

<details>
<summary>What is "space sharing"?</summary><br><b>

Somewhat the opposite of time sharing. While in time sharing a resource is used for a while by one entity and then the same resource can be used by another resource, in space sharing the space is shared by multiple entities but in a way it's not being transfered between them.<br>
It's used by one entity until this entity decides to get rid of it. Take for example storage. In storage, a file is your until you decide to delete it.
</b></details>

## Ansible

<a name="ansible-beginner"></a>

<details>
<summary>Describe each of the following components in Ansible, including the relationship between them:

- Task
- Module
- Play
- Playbook
- Role</summary><br><b>

Task – a call to a specific Ansible module
Module – the actual unit of code executed by Ansible on your own host or a remote host. Modules are indexed by category (database, file, network, …) and also referred as task plugins.

Play – One or more tasks executed on a given host(s)

Playbook – One or more plays. Each play can be executed on the same or different hosts

Role – Ansible roles allows you to group resources based on certain functionality/service such that they can be easily reused. In a role, you have directories for variables, defaults, files, templates, handlers, tasks, and metadata. You can then use the role by simply specifying it in your playbook.
</b></details>

<details>
<summary>How Ansible is different from other Automation tools?</summary><br><b>

Ansible is:

- Agentless
- Minimal run requirements (Python & SSH) and simple to use
- Default mode is "push" (it supports also pull)
- Focus on simpleness and ease-of-use
  </b></details>

<details>
<summary>What kind of automation you wouldn't do with Ansible and why?</summary><br><b>

While it's possible to provision resources with Ansible it might not be the best choice for doing so as Ansible doesn't
save state by default and a task that creates 5 instances, when executed again will create additional 5 instances (unless
additional check is implemented).
</b></details>

<details>
<summary>What is an inventory file and how do you define one?</summary><br><b>

An inventory file defines hosts and/or groups of hosts on which Ansible tasks executed upon.

An example of inventory file:

```
192.168.1.2
192.168.1.3
192.168.1.4

[web_servers]
190.40.2.20
190.40.2.21
190.40.2.22
```

</b></details>

<details>
<summary>What is a dynamic inventory file? When you would use one?</summary><br><br>

A dynamic inventory file tracks hosts from one or more sources like cloud providers and CMDB systems.

You should use one when using external sources and especially when the hosts in your environment are being automatically<br>
spun up and shut down, without you tracking every change in these sources.
</b></details>

<details>
<summary>How do you list all modules and how can you see details on a specific module?</summary><br><br>

1. Ansible online docs
2. `ansible-doc -l` for list of modules and `ansible [module_name]` for detailed information on a specific module
   </b></details>

<details>
<summary>Write a task to create the directory ‘/tmp/new_directory’</summary><br><b>

```
- name: Create a new directory
  file:
    path: "/tmp/new_directory"
    state: directory
```

</b></details>

<details>
<summary>You want to run Ansible playbook only on specific minor version of your OS, how would you achieve that?</summary><br><b>
</b></details>

<details>
<summary>What the "become" directive used for in Ansible?</summary><br><b>
</b></details>

<details>
<summary>What are facts? How to see all the facts of a certain host?</summary><br><b>
</b></details>

<details>
<summary>What would be the result of the following play?</summary><br><b>

```
---
- name: Print information about my host
  hosts: localhost
  gather_facts: 'no'
  tasks:
      - name: Print hostname
        debug:
            msg: "It's me, {{ ansible_hostname }}"
```

When given a written code, always inspect it thoroughly. If your answer is “this will fail” then you are right. We are using a fact (ansible_hostname), which is a gathered piece of information from the host we are running on. But in this case, we disabled facts gathering (gather_facts: no) so the variable would be undefined which will result in failure.
</b></details>

<details>
<summary>What would be the result of running the following task? How to fix it?

```
- hosts: localhost
  tasks:
      - name: Install zlib
        package:
          name: zlib
          state: present
```

</summary><br><b>
</b></details>

<details>
<summary>Which Ansible best practices are you familiar with?. Name at least three</summary><br><b>
</b></details>

<details>
<summary>Explain the directory layout of an Ansible role</summary><br><b>
</b></details>

<details>
<summary>What 'blocks' are used for in Ansible?</summary><br><b>
</b></details>

<details>
<summary>How do you handle errors in Ansible?</summary><br><b>
</b></details>

<details>
<summary>You would like to run a certain command if a task fails. How would you achieve that?</summary><br><b>
</b></details>

<details>
<summary>Write a playbook to install ‘zlib’ and ‘vim’ on all hosts if the file ‘/tmp/mario’ exists on the system.</summary><br><b>

```
---
- hosts: all
  vars:
      mario_file: /tmp/mario
      package_list:
          - 'zlib'
          - 'vim'
  tasks:
      - name: Check for mario file
        stat:
            path: "{{ mario_file }}"
        register: mario_f

      - name: Install zlib and vim if mario file exists
        become: "yes"
        package:
            name: "{{ item }}"
            state: present
        with_items: "{{ package_list }}"
        when: mario_f.stat.exists
```

</b></details>

<details>
<summary>Write a single task that verifies all the files in files_list variable exist on the host</summary><br><b>

```
- name: Ensure all files exist
  assert:
    that:
      - item.stat.exists
  loop: "{{ files_list }}"
```

</b></details>

<details>
<summary>Write a playbook to deploy the file ‘/tmp/system_info’ on all hosts except for controllers group, with the following content</summary><br><b>

```
I'm <HOSTNAME> and my operating system is <OS>
```

Replace <HOSTNAME> and <OS> with the actual data for the specific host you are running on

The playbook to deploy the system_info file

```
---
- name: Deploy /tmp/system_info file
  hosts: all:!controllers
  tasks:
      - name: Deploy /tmp/system_info
        template:
            src: system_info.j2
            dest: /tmp/system_info
```

The content of the system_info.j2 template

```
# {{ ansible_managed }}
I'm {{ ansible_hostname }} and my operating system is {{ ansible_distribution }
```

</b></details>

<details>
<summary>The variable 'whoami' defined in the following places:

- role defaults -> whoami: mario
- extra vars (variables you pass to Ansible CLI with -e) -> whoami: toad
- host facts -> whoami: luigi
- inventory variables (doesn’t matter which type) -> whoami: browser

According to variable precedence, which one will be used?</summary><br><b>

The right answer is ‘toad’.

Variable precedence is about how variables override each other when they set in different locations. If you didn’t experience it so far I’m sure at some point you will, which makes it a useful topic to be aware of.

In the context of our question, the order will be extra vars (always override any other variable) -> host facts -> inventory variables -> role defaults (the weakest).

A full list can be found at the link above. Also, note there is a significant difference between Ansible 1.x and 2.x.
</b></details>

<details>
<summary>For each of the following statements determine if it's true or false:

- A module is a collection of tasks
- It’s better to use shell or command instead of a specific module
- Host facts override play variables
- A role might include the following: vars, meta, and handlers
- Dynamic inventory is generated by extracting information from external sources
- It’s a best practice to use indention of 2 spaces instead of 4
- ‘notify’ used to trigger handlers
- This “hosts: all:!controllers” means ‘run only on controllers group hosts</summary><br><b>
  </b></details>

<details>
<summary>What is ansible-pull? How is it different from how ansible-playbook works?</summary><br><b>
</b></details>

<details>
<summary>What is Ansible Vault?</summary><br><b>
</b></details>

<details>
<summary>Demonstrate each of the following with Ansible:

- Conditionals
- Loops
  </summary><br><b>
  </b></details>

<a name="ansible-advanced"></a>

<details>
<summary>What are filters? Do you have experience with writing filters?</summary><br><b>
</b></details>

<details>
<summary>Write a filter to capitalize a string</summary><br><b>

```
def cap(self, string):
    return string.capitalize()
```

</b></details>

<details>
<summary>You would like to run a task only if previous task changed anything. How would you achieve that?</summary><br><b>
</b></details>

<details>
<summary>What are callback plugins? What can you achieve by using callback plugins?</summary><br><b>
</b></details>

<details>
<summary>File '/tmp/exercise' includes the following content

```
Goku = 9001
Vegeta = 5200
Trunks = 6000
Gotenks = 32
```

With one task, switch the content to:

```
Goku = 9001
Vegeta = 250
Trunks = 40
Gotenks = 32
```

</summary><br><b>

```
- name: Change saiyans levels
  lineinfile:
    dest: /tmp/exercise
    regexp: "{{ item.regexp }}"
    line: "{{ item.line }}"
  with_items:
    - { regexp: '^Vegeta', line: 'Vegeta = 250' }
    - { regexp: '^Trunks', line: 'Trunks = 40' }
    ...
```

</b></details>

#### Ansible Testing

<details>
<summary>How do you test your Ansible based projects?</summary><br><b>
</b></details>

<details>
<summary>What is Molecule? How it works?</summary><br><b>
</b></details>

<details>
<summary>You run Ansibe tests and you get "idempotence test failed". What does it mean? Why idempotence is important?</summary><br><b>
</b></details>
