
# CrewAI Debate Project

## Description (FR / EN)

🇫🇷 Ce projet utilise CrewAI pour organiser un débat argumentatif entre deux agents intelligents : un débatteur et un juge.  
Le but est d'évaluer et de simuler des débats logiques sur divers sujets automatiquement.

🇬🇧 This project leverages CrewAI to simulate a structured argumentative debate between two AI agents: a debater and a judge.  
The goal is to evaluate opposing perspectives on a motion and determine the winner based on logic and persuasiveness.

## Demo

You can watch a demonstration of the debate app in action here:  
[Demo Video](https://drive.google.com/file/d/1FrPSzPUAdWhElit5ok5NLdRLHml86Q4U/view)

## Agents Configuration

- **debater**  
  A compelling debater with a knack for persuasive arguments.  
  Goal: Present clear and compelling arguments for or against the motion to persuade the audience.

- **judge**  
  An impartial judge with a keen sense of fairness and justice.  
  Goal: Evaluate the arguments presented by both sides on the motion and determine the winner based on clarity, logic, and persuasiveness.

## Tasks

- **propose**  
  Propose a motion that is relevant and interesting, suitable for a detailed report.  
  Deliver a clear and concise proposal including a strong argument in favor of the motion.

- **oppose**  
  Present a convincing argument against the motion.  
  Deliver a clear and concise proposal including a strong argument against the motion.

- **decide**  
  Review the arguments for and against the motion and decide which side has the stronger argument.  
  Deliver a clear and concise decision including a strong argument for your conclusion.

## Installation

Ensure you have Python >=3.10 <3.14 installed on your system. This project uses [UV](https://docs.astral.sh/uv/) for dependency management and package handling, offering a seamless setup and execution experience.

First, if you haven't already, install uv:

```bash
pip install uv
```

Next, navigate to your project directory and install the dependencies:

(Optional) Lock the dependencies and install them by using the CLI command:
```bash
crewai install
```
### Customizing

**Add your `OPENAI_API_KEY` into the `.env` file**

- Modify `src/crewaiapp/config/agents.yaml` to define your agents
- Modify `src/crewaiapp/config/tasks.yaml` to define your tasks
- Modify `src/crewaiapp/crew.py` to add your own logic, tools and specific args
- Modify `src/crewaiapp/main.py` to add custom inputs for your agents and tasks


By default, the test input used for the debate motion is in main.py:

```python
inputs = {
    'motion': 'There needs to be strict laws to regulate the use of AI LLMs.',
}
```
You can modify this input to change the motion and explore different debate topics. The agents will then generate arguments based on the new motion, and the judge will evaluate accordingly.


## Running the Project

To run the project, use the following command from the root directory:

```bash
crewai run
```

This will start the CrewAI debate process using your configured agents and tasks. The results will be saved in a `report.md` file in the root folder.

To kickstart your crew of AI agents and begin task execution, run this from the root folder of your project:

```bash
$ crewai run
```

This command initializes the CrewAIApp Crew, assembling the agents and assigning them tasks as defined in your configuration.

This example, unmodified, will run the create a `report.md` file with the output of a research on LLMs in the root folder.

## Understanding Your Crew

The CrewAIApp Crew is composed of multiple AI agents, each with unique roles, goals, and tools. These agents collaborate on a series of tasks, defined in `config/tasks.yaml`, leveraging their collective skills to achieve complex objectives. The `config/agents.yaml` file outlines the capabilities and configurations of each agent in your crew.
