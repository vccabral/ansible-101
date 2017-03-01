Facts, Variables and Vault
===

Facts are just like english. They are a fact about a host or a fact about a play during a specific scope of the playbook. You can use a debug statement to give print out the variable in a specific scope.

http://docs.ansible.com/ansible/debug_module.html

```
- name: Display all variables/facts known for a host
  debug:
    var: hostvars[inventory_hostname]
    verbosity: 4
```

Variables can be set at many levels but we will go over the most common places.
* https://github.com/geerlingguy/ansible-role-apache

Let's look at the anatomy of a ansible playbook and the assumptions it makes. Here is a typical structure.

* defaults
* files
* handlers
* meta
* tasks
* templates
* vars

Each of these folders have convention of configuration purpose. As you investigate more into ansible, you will get more comfortable with each of these folders but let's start with the basics.

Each of these folders, if it exists, will be picked up by an ansible play, IF there is a file named main.yml inside that folder. What does that look like now?

* defaults
** main.yml
* files
** NOT SO FAST
* handlers
** main.yml
* meta
** main.yml
* tasks
** main.yml
* templates
** NOT SO FAST
* vars
** main.yml

The files and tmeplates directories are the exception. The templates/files directories are default search locations. When the file or template module are used, the playbook will look for files and templates inside those directories.


