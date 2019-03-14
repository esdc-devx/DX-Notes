# GitLab-Runner ITAM Request 
https://docs.gitlab.com/runner/

## General Product Functionality
Pulls specificed GitLab repositories for changes and runs a series of 'jobs' and commands defined in that repository within an isolated enviornment defined by the commands. 
Typically those commands will consist of compile, testing, packaging and deploying stages. 
It will send the results of those 'jobs' and commands back to GitLab.
GitLab-Runner will also allow us to make use of GitLab's Audo DevOps allowing us to stand up fully featured CI/CD pipelines with minimal work.
It also has powerfull integrations with Kubernetes and Docker enabling the transition to those tools in our future much simpler.

## Business Rational

### Business Drivers 

- We need more modern software development tools that keep pace with industry standards.  
- We need tools that integrate with other tools that are industry standards while preventing us from vender lock-in.  
- We specifically need a tool that handles pipeline management far better than the existing tools which fail to fully meet the above stated business drivers. 

### Business Functionality Requirements 

We need a tool that can: 
- run a single 'job' from a pipeline in an isolated/standalone fully functional environment; 
- spin up a container within a single 'job' in the pipeline; 
- execute any kind of testing framework and generate reports on that; 
- integrate effectively with the source control environment being used by the development team; 
- deploy compiled solutions to multiple environments (SADE, SSC and Cloud) and report on the version and status of that deployment; 
- integrate the pipeline definition into the source code versioning; 
- handel running a pipeline on multiple branches created on the fly.

### Historical Background / Current Situation 

Currently we have two tools, TFS and Jenkins, that meet parts of the Business Drivers and Business Functionality Requirements but not all of them. 
These tools have been around for a very long time in ESDC and have proven to be tolerable given our outdated standards for development. 
SSC has stood up an instance of GitLab Community Edition (free under the MIT license) notably known as GCCode available for all government departments to collaborate and use. 
ESDC has started to use GCCode for many of our solutions. 
We have been able to integrate GCCode with TFS and Jenkins, but because these tools were not designed to work together, we have encountered many problems and need a suitable solution to go forward. 
With research and proof-of-concepts, GitLab-Runner (free under the MIT license) has proven its self to be far more effective than the current tools; even in their most optimized setup. 
GCCode is planning to allow the use of shared runners hosted by the owner of GCCode (currently SSC, expected to be PSPC in the near future) and integration of GitLab with our cloud infrastructure. 
Having access to gitlab-runner now will help build capacity with the tool for when these features are enabled.

This request is coming from the Developer Experince team tasked by senior management up to the director general level to improve the developer experince; and we believe that this tool is critial to the department in moving us forward with modern software development.

## Alternative Products

### TFS Release Manager

#### Pros
- Integrates with TFS
- Existing in department

#### Cons
- Doesn't have native integration with GCCode (GitLab)
- Rebuilds for each enviornment
- Cumbersome UI with no alternative
- Managed seperate from source
- Difficult to do use for customized applications
- Lots of restrictions to managing the release (set in place by SADE)
- Non-issolated 'jobs'
- Limited default testing tools

### Jenkins / Maven

#### Pros
- Existing in department
- Meets most of the Business Functionality Requirements

#### Cons
- Doesn't have native integration with GCCode (GitLab)
- Outdated when dealing with containers, doesn't provide full funtionality

## Connections Diagram
**Legend**  
Black: Existing state  
Green: New with GitLab-Runner installs  
Blue: Potiential future state

### Basic introduction diagram
![Connections Diagram](https://github.com/esdc-devx/DX-Notes/blob/master/software-requests/gitlab-runner/GitLab-Runner_ConnectionDiagram.PNG)


### Diagram with potential cloud integration
![Connections Diagram With Cloud](https://github.com/esdc-devx/DX-Notes/blob/master/software-requests/gitlab-runner/GitLab-Runner_ConnectionDiagram_WithCloud.PNG)
