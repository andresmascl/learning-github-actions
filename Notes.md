YAML = Yaml Ain't a Markup Language! XD

Jobs have:
    `name` field.  Only contains alphanumeric or - or _
    `on` field (e.g. on: [`push`])
    `jobs`: An array of steps.  Each has:
        A string consisting of the step's name (e.g. `say-hello`).  Each one 
        has:
            `runs-on`: A field indicating the OS the job runs on (a Docker  
                image) (e.g. `ubuntu-latest`). Can be:
                    Windows Server 2019
                    Ubuntu 18.04
                    Ubuntu 16.04
                    macOS Catalina 10.15
                    Self-hosted Runners
            `steps`: An array with steps to execute.  By default they runn 
                asyncronously.
            - `name`: The name of the step (e.g. Checkout).  If you dont specify
                one, the worflow will use the text from the action or command 
                instead
              `uses`: (E.g. `actions/checkout@v2.0.0`) defines the Docker image 
                    that will run the Action.  They can be located in the same 
                    repository as the workflow, in another github repository, 
                    or in a container registry.  
            - `run`: If we aren't using an action we can use `run` to specify 
                shell commands (e.g. echo Hello, world!)

Workflows are stored in `.github/workflows`
    Each workflow must have at least one job.  And each job must have at least
    one identifier.  By default jobs run in parallel.
    By default the run commands are interpreted by Bash.
    

