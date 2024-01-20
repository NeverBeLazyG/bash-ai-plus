# Bash AI

Bash AI _(bai)_ is a bash shell script that acts as an AI assistant, inspired by [Your AI _(yai)_](https://github.com/ekkinox/yai).\
Leveraging OpenAI's capabilities, it allows you to ask questions and perform terminal-based tasks using natural language. It provides answers and command suggestions based on your input and allows you to execute or edit the suggested commands if desired.

## Features

Bash AI offers the following features:

- **Natural Language Interface**\
	Communicate with the terminal using everyday language.
	
- **Question Answering**\
	Get answers to all your terminal questions by ending your request with a question mark.

- **Command Suggestions**\
	Receive intelligent command suggestions based on your input.

- **Command Information**\
	Get detailed information about the suggested commands.
	
- **Distribution Awareness**\
	Get answers and commands that are compatible with, and related to, your specific Linux distribution.

- **Command Execution**\
	Choose to execute the suggested commands directly from Bash AI.

- **Command Editing**\
	Edit the suggested commands before execution.

- **Error Examination**\
	Examine the error messages generated by the suggested commands and attempt to fix them.

- **Persistent Memory**\
	In Interactive Mode, Bash AI remembers your previous requests and uses them to improve future suggestions.

## Installation

<details open>
<summary><b>Quick Start</b></summary>

* To install Bash AI quickly, you can run the following command:

```bash
curl -sS https://raw.githubusercontent.com/hezkore/bash-ai/main/install.sh | bash
```

</details>

<details>
<summary><b>Manual Installation</b></summary>

1. Clone or download the repository:

	```bash
	git clone https://github.com/hezkore/bash-ai.git
	```
2. Make the script executable:

	```bash
	chmod +x bai.sh
	```

3. Execute Bash AI:

	```bash
	./bai.sh
	```

*  _(Optional)_ For convenience, you can create a shortcut to the `bai.sh` script. There are two ways to do this:

	* Create a symbolic link in `/usr/local/bin`. This will allow you to run the script from anywhere, without having to type the full path. Replace `path/to/bai.sh` with the actual path to the `bai.sh` script:

		```bash
		ln -s path/to/bai.sh /usr/local/bin/bai
		```

	* Alternatively, you can create an alias for the `bai.sh` script in your `.bashrc` file. This will also allow you to execute the script using the `bai` command, reducing the need for typing the full path to the script each time. Replace `path/to/bai.sh` with the actual path to the `bai.sh` script:

		```conf
		alias bai='path/to/bai.sh'
		```

</details>

## Configuration

On the first run, a configuration file named `bai.cfg` will be created in your `~/.config` directory.\
You must provide your OpenAI key in the `key=` field of this file. The OpenAI key can be obtained from your OpenAI account.

> [!CAUTION]
> Keeping the key in a plain text file is dangerous, and it is your responsibility to keep it secure.

You can also change the model, temperature and query in this file.

> [!TIP]
> The `gpt-4` models produce much better results than the standard `gpt-3.5-turbo` model.

## Usage

Bash AI operates in two modes: Interactive Mode and Command Mode.

To enter Interactive Mode, you simply run `bai` without any request. This allows you to continuously interact with Bash AI without needing to re-run the command.

In Command Mode, you run `bai` followed by your request, like so: `bai your request here`

Example usage:

```
bai create a new directory with a name of your choice, then create a text file inside it
```

You can also ask questions  by ending your request with a question mark:
```
bai what is the current time?
```

## Known Issues

- In Command Mode, avoid using single quotes in your requests.\
	For instance, the command `bai what's the current time?` will not work. However, both `bai "what's the current time?"` and `bai what is the current time?` will execute successfully.\
	Please note that this issue is specific to the terminal, and does not occur in Interactive Mode.

## Prerequisites

- [OpenAI account and API key](https://platform.openai.com/apps)
- [curl](https://curl.se/download.html)
- [jq](https://stedolan.github.io/jq/download/)