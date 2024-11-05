# Summary
The system can output a given Japanese presentation video/audio as audio translated into English. Corresponding scripts are also output. This can be run on Google Colaboratory.

# Usage
Run main.ipynb written in Jupyter Notebook format.
When you run main(), you will be asked for the path to the file, so enter that (can be local or remote).

Read the given file, this program will execute

1. Japanese transcription (SpeechFlow)
2. Japanese modification (ChatGPT)
3. translate Japanese into English (Deepl)
4. English speech synthesis

The audio and scripts are output to the output folder (If the output folder does not exist, it is automatically generated in the root directory).

# Preparation
## Common to all
Before use this program, you need to import the libraries described in requirements.txt.

This one is basically intended to run on Google Colaboratory.
If you want to run it in your local environment, please change the following variables to suit your environment.

- env_path
- context_path
- prompt_fix_jp_path (optional)
- output_dir

## API related
Also, create `.env` file in root directory and write variables (API keys) as follows:

### SpeechFlow
- SPEECHFLOW_API_KEY_ID="hogehoge"
- SPEECHFLOW_API_KEY_SECRET=hogehoge"
### OpenAI ChatGPT
- OPENAI_API_KEY="hogehoge"
### Genny
- GENNY_API_URL="hogehoge"
- GENNY_API_KEY="hogehoge""
- GENNY_SPEAKER="hogehoge""
- GENNY_SPEAKER_STYLE="hogehoge""
### Deepl
DEEPL_AUTH_KEY="hogehoge"

## Note on API
This system uses the API of the following services:

- [SpeechFlow](https://docs.speechmatics.com/flow/flow-api-ref) - A real-time speech-to-text API service with live audio streaming capabilities[1]
- [OpenAI](https://platform.openai.com/docs/api-reference) - Provides various AI models including GPT for text generation and analysis[2]
- [DeepL](https://github.com/DeepLcom/deepl-python) - High-quality language translation API with support for multiple languages[3]
- [Genny](https://github.com/cheekybits/genny) - A code-generation tool for Go that enables generic programming[4]

Each service provides specific functionalities:
- SpeechFlow handles real-time audio transcription and processing[1]
- OpenAI offers advanced language models and AI capabilities[2]
- DeepL provides professional-grade translation services[3]
- Genny facilitates code generation and generic programming[4]