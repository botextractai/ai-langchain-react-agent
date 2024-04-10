# LangChain ReAct agent with multiple tools (Python REPL and DuckDuckGo Search)

This project works with the [OpenAI GPT-3.5 Turbo](https://platform.openai.com/docs/models/gpt-3-5-turbo) Large Language Model (LLM). However, you can also use other OpenAI models that have been trained to handle function calls.

You need an OpenAI API key for this project. [Get your OpenAI API key here](https://platform.openai.com/login). Insert your OpenAI API key in the "ai-langchain-react-agent.py" script.

Agents give decision-making powers to Large Language Models (LLMs) and decide which action(s) to take to get the best answer. An Agent can use one or multiple specific "tools". Depending on what the user input (prompt) is, the agent may or may not call any of these tools, or even multiple tools in a row, until it can reason its way to the answer.

This project uses a ReAct type of agent, which uses the ReAct framework or model for prompting. The basic idea is that the model does Reasoning, which is the Re part, and based on that reasoning it takes Action, which is the Act part. Then based on the result of the action, or its observation, it will go and reason again.

Tools are the name LangChain uses for what are basically a type of function calls that can run a specific action and return the result. LangChain offers many pre-built tools, but also allows you to build your own tools.

A Read-Eval-Print Loop (REPL), is a computer environment where user inputs are read and evaluated, and then the results are returned to the user. PythonAstREPLTool is one of the predefined tools that LangChain comes with. It is a tool that will run a Python REPL session and return the output. It is used for complex mathematical calculations, which are often a weakness of LLMs. Python REPL is probably the most powerful of all tools, because it can execute Python program code, such as Python functions. This allows you to use your own applications.

The DuckDuckGo Search tool is used to search the internet. It does much of the same as "SERP" API's, but it does not require any kind of sign up or payment. This tool is most commonly used to find information that is newer than the cut-off date of the LLM training data.

## Some example questions

You can copy and paste the example questions from this table to replace the question at the bottom of the "ai-langchain-react-agent.py" script. This allows you to verify, if the agent uses the best tool for the question.

| Expected Tool     | Question                                                                                                                             |
| ----------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| Python REPL       | `"What is the result of this python code: '47a93.isalnum()'?"`                                                                       |
| DuckDuckGo Search | `"What is the Microsoft (MSFT) share price?"`                                                                                        |
| LLM (no tool)     | `"A boy runs down the stairs in the morning and sees a tree in his living room, and some boxes under the tree. What's is going on?"` |
