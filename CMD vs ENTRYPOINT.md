
# Difference between CMD vs ENTRYPOINT
![Alt Text](https://devopsmania.com/wp-content/uploads/2022/02/benim-696x351.jpg)

# CMD Instruction 
You can set default commands with parameters using the CMD instruction. If you run a Docker
container without specifying any additional CLI commands, the CMD instruction will be executed.
You can include an executable as the default command. However, if you choose to omit it, you will
have to specify an ENTRYPOINT instruction along with the CMD instruction

If you have specified an argument along with the Docker run command, the default one specified
using the CMD instruction will be ignored. Also, if you have specified multiple CMD instructions
inside a single dockerfile, the one specified at the last will only be executed.

The CMD instruction has three forms -

 *CMD ["only_executable","parameter_1","parameter_1"] (executable form)*

 *CMD ["parameter_1","parameter_2"] (used to provide default parameters to the ENTRYPOINT instruction)*

 *CMD command param1 param2 (It is the shell form)*

**Example -**

 *$ CMD echo "Command in Shell Form"*

 *$ CMD ["/bin/bash", "-c", "echo Command in Exec Form"]*

# ENTRYPOINT Instruction
The ENTRYPOINT instruction looks almost similar to the CMD instruction. However, the main highlighting 
difference between them is that it will not ignore any of the parameters that you have specified in the
Docker run command (CLI parameters).

When we have specified the ENTRYPOINT instruction in the executable form, it allows us to set or define
some additional arguments/parameters using the CMD instruction in Dockerfile. If we have used it in the
shell form, it will ignore any of the CMD parameters or even any CLI arguments.
The forms of the ENTRYPOINT Instruction are -
 *ENTRYPOINT ["only_executable", "parameter_1", "parameter_2"] (executable form)*

 *ENTRYPOINT command parameter_1 parameter_2 (Shell form)*

**Example -**

 *$ ENTRYPOINT echo "Welcome to TutorialsPoint"*

 *$ ENTRYPOINT ["/bin/bash", "-c", "echo Welcome to TutorialsPoint"]*



