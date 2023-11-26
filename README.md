## [Super Quick: In-Context Learning with personal data using LLAMA 2.0 on CPU](https://python.plainenglish.io/super-quick-fine-tuning-llama-2-0-on-cpu-with-personal-data-d2d284559f)

### Software Specs
- Operating System: Ubuntu preferably
- Python: version 3.10 and above
- Model: Quantized [llama-2–7B-Chat-GGML](https://huggingface.co/TheBloke/Llama-2-7B-Chat-GGML/blob/main/llama-2-7b-chat.ggmlv3.q8_0.bin) (so that it can run on CPU)
- Vector Data Store: FAISS
- Transformer: CTransformer
- Deployment: Chainlit

### Hardware Requirement
- Hard Disk Space: The llama model is ~7GB, the rest is your data.
- RAM: 16GB at least (8 GB will fail after one or two questions)

### Setup Project
- Download the llama2 model into the root folder. The model is linked above.
- Run `pip install -r requirements.txt`
- Create a `data` folder and move all required pdf files into it
    - I have used pdf files from [TKN Siddha Ayurveda Vaidyashala](https://www.tknsiddha.com/medicine/ayurveda-english-e-books/)
- Data processing: Run `python data_process.py` which will generate embeddings in a folder named `vectorstores`
- Deploy Mode (use one of the below options): 
  - Run `chainlit run deploy.py -w` <br>
    OR
  - Run `python -m chainlit run deploy.py -w`
- App will be available on http://localhost:8000