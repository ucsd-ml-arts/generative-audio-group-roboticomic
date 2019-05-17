# Project 3 Generative Audio

Roy Jara, rjara@ucsd.edu
Elliott Lao, eylao@ucsd.edu

## Abstract

Include your abstract here. This should be one paragraph clearly describing your concept, method, and results. This should tell us what architecture/approach you used. Also describe your creative goals, and whether you were successful in achieving them. Also could describe future directions.

Our concept was to create a robotic stand up comedian that tells one to two liner jokes. For the joke generation portion of the project, we used the character rnn demoed earlier in the class with the addition of two additonal RNN layers and trained it on a collection of jokes found on Kaggle and oneliners scraped from Reddit. We then fed the generated jokes into the TacoTron/Waveglow example for text to speech and generated a .wav file. After this we stiched on an generated laughing sound at the end of the joke to complete the joke. The jokes that the neural net makes aren't entirely exactly coherent, but they do have comedic value and sometimes elicit laughter. We had originally wanted to fully automate the process of generating spoken jokes combining them with the laughter. Unfortunatley we ran into some trouble exporting the .wav files and ended up partially doing the process manually.  Future directons that we could take the project are Alexa skills or an "easy button" like contraption. 


## Model/Data

Briefly describe the files that are included with your repository:
- Wavenet
- training data 
  - oneliners.tsv, jokes scraped from reddit (r/oneliners) 
  - jokes.csv, questiona and answer two-liner joke repository (https://www.kaggle.com/jiriroz/qa-jokes)
  - Laugh Wav files from a Kaggle Competition https://www.kaggle.com/c/freesound-audio-tagging/data



## Code

Your code for generating your project:
- CharRNN:
  -char_rnn_QA.ipynb and char_rnn_onliners.ipynb, these files almost the same and are based on the character rnn example in project 1.
- Tacotron2:
  -tacotron_waveglow_tts.ipynb, this file is based upon the tacotron2 tts example code with an additional text cleaning function.

- Python: generative_code.py
- Jupyter notebooks: 
  - PRAW Scraping.ipynb, this file is used for scraping the "top" 1000 posts from a specific subreddit

## Results

Documentation of your results in an appropriate format, both links to files and a brief description of their contents:
- Our results are in a .wav file format, put together like a stand-up comic's set (a really bad standup comic)


## Technical Notes

Any implementation details or notes we need to repeat your work. 
- Does this code require other pip packages, software, etc?
  The Reddit scraping portion of the code requires praw and pandas, otherwise the code should run on packages already included and used in example code.
- Does it run on some other (non-datahub) platform? (CoLab, etc.)
  Our code runs on just datahub.

## Reference

References to any papers, techniques, repositories you used:
- Papers
- Repositories
- Blog posts
https://www.kaggle.com/jiriroz/qa-jokes
https://www.kaggle.com/c/freesound-audio-tagging/data
