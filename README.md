# Github Action Runner :runner:

Run Github Action Runner self-hosted on your machine using Docker container.

#### Example use

Set your environment variables on `.env` file or using `export`.
```
export runnerName=<yourRunnerName>
export repoURL=<yourRepositoryURL>
export runnerToken=<yourRepositoryToken>
export runnerWorkDir=<yourRunnerWorkDirectory>
```

Start your Action Runner manually using Docker CLI command.
```
docker run -d --restart always --name $runnerName \
    -e REPO_URL=$repoURL \
    -e RUNNER_NAME=$runnerName \
    -e RUNNER_TOKEN=$runnerToken \
    -e RUNNER_WORKDIR=$runnerWorkDir \
    -v /var/run/docker.sock:/var/run/docker.sock \
    mataberat/github-runner:latest
```

Or using `docker-compose`.
```
docker-compose up -d
```