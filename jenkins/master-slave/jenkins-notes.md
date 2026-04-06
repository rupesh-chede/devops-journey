# Jenkins Master-Slave (Controller-Agent) Architecture

## What is Jenkins Master?
- Main server / brain of Jenkins
- Schedules jobs
- Manages pipelines
- Stores config & logs
- Serves UI on port 8080
- Listens for agents on port 50000

## What is Jenkins Slave (Agent)?
- Separate machine that runs builds
- Receives instructions from master
- Executes shell commands & tests
- Reports results back to master
- Can be: VM, physical machine, Docker, cloud

## Master ↔ Agent Communication
- SSH: Master connects to agent
- JNLP: Agent calls back to master (port 50000)

## Setup Steps
1. Install Jenkins on Master
2. Install Java on Agent
3. Create jenkins user on Agent
4. Setup SSH keys Master → Agent
5. Add Node in Jenkins UI
6. Label agents (linux, docker, windows)

## Pipeline Example
pipeline {
    agent { label 'linux' }
    stages {
        stage('Build') {
            steps {
                sh 'echo Building...'
            }
        }
    }
}

## Best Practices
- Never run builds on master
- Label all agents properly
- Use Docker agents for clean builds
- Scale horizontally by adding agents
