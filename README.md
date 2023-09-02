# Video-Transcript-Summarizer

Step 1: Change the runtime environment of Google Colab notebook to T4 GPU from CPU.

Step 2: install the requirements.txt file by,
      ! pip install -r requirements.txt

Step 3: We import the pipeline module from the Transformers library

Step 4: We extract the Youtube video in '.mp4' format download it in teh notebook itself
        and then convert it to '.mp3' or '.wav' format with the moviepy library.

Step 5: We use the HuggingFace pipeline of "Automatic-Speech-Recognition" and the model of 
        either 'jonatasgrosman/wav2vec2-large-xlsr-53-english' or 'facebook/wav2vec2-base-960h' as the performing model.

Step 6: We then used the trained model to transcribe the converted Audio file.

Step 7: Now the transcribed text output is in Dictionary format, simce the "Summarizer" pipeline only works on lists or arrays, 
        we convert the dictionary to list data structure.

Step 8: Now we use the list for the 'Summarizer' pipeline which used the model 'facebook/bart-large-cnn' as evaluating metric.

Step 9: Finally we display the summarized the text.



Note: If sometimes the GPU runs out of memory , we could chunk the audio file into chuncks of either 30 seconds or 45 seconds using the Librosa library.
We then collect the chunks in an array and use these chunks to train the model. Althought the training time would be increased, but the GPU in the free version
of Google Colab doesn.t run out of memory.

This method of braking the audio fie into chunks of 30 seconds is demonstrated in the other notebook "Youtube_Video_Summarization_with_Hugging_Face_ASR"
