# Coding Standards #
## Docker ##

### Description ###

This container to for running coding standard tests on applications.


### Running ###

By default this will just give you a shell to do whatever you like in.
For actual testing you will have to replace the brackets at the end of the command with the command and options you wish to use for testing.

```bash
docker run -it -v `pwd`:/var/www --rm --name coding-standards registry.drp.digital/coding-standards <command to run to test code>
```

This will mount your current working directory inside the container,

Name the container "coding-standards" for easy docker management and removal (you can change this to any name you like)

Use the version of coding-standards in the drp docker registry

#### Example ####

Example of running this on a laravel project from the directory of the project:
```bash
docker run -it -v `pwd`:/var/www --rm --name coding-standards registry.drp.digital/coding-standards phpcs --standard=psr2 ./app -p --colors --ignore='*/*.blade.php
```

### Notes ###

Commands available are:
- phpcs
- phpcbf
- phpmd
