# ollama
Ollama script, configuration, etc..
# Install

    curl -fsSL https://ollama.com/install.sh | sh

[Manual install instructions](https://github.com/ollama/ollama/blob/main/docs/linux.md)

## Services

The file of service configuration is :   
> /etc/systemd/system/ollama.service

The models will be store to : 

* /usr/share/ollama/.ollama/models   
* /root/.ollama/models   
* /user/.ollama/models   

You must change or add this line for :

***Modify the listen IP***    
``Environment="OLLAMA_HOST=0.0.0.0:11434"``

***Modify the models path***
``Environment="OLLAMA_MODELS=/your/new/path/models"``

***Docker***

The official [Ollama Docker image](https://hub.docker.com/r/ollama/ollama) ollama/ollama is available on Docker Hub.


# How to Change the Ollama Model Directory

## Setting Up the Environment Variable
One effective method of changing the model location involves using the
OLLAMA_MODELS
environment variable. Here’s how you can do it:

Open Terminal / Command Prompt: Depending on your OS, you may need to navigate to the terminal (macOS/Linux) or Command Prompt (Windows).
Set the Environment Variable: Use the following command:

***For Linux/macOS:***

bash    
``export OLLAMA_MODELS=/path/to/your/custom/directory``

***For Windows:***
Open the settings, access the environment variables, and create a new variable named ***OLLAMA_MODELS*** pointing to your desired directory. You can do this via the Command Prompt too:

cmd    
```setx OLLAMA_MODELS D:\path\to\your\directory```

This pathway will redirect Ollama to use the new directory for storing models.


## Use of Symbolic Links

If you face any issues with the environment variable method, an alternative approach is creating a symbolic link:

    Navigate to the default Ollama models directory.
    Remove the existing models directory:

bash    
 ``rm -r /usr/share/ollama/.ollama/models``

Create a new symbolic link:

bash    
 ``ln -s /home/yourusername/path/to/new/models /usr/share/ollama/.ollama/models``

# Sources:

[Github](https://github.com/ollama/ollama/tree/main)
