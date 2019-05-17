# Project 3 Generative Audio

Roy Jara, rjara@ucsd.edu

Elliott Lao, eylao@ucsd.edu

## Abstract

Include your abstract here. This should be one paragraph clearly describing your concept, method, and results. This should tell us what architecture/approach you used. Also describe your creative goals, and whether you were successful in achieving them. Also could describe future directions.

Our concept was to create a robotic stand up comedian (and audience) that tells one/two liner jokes, both the jokes and corresponding laughter from the audience would be computer generated. For the joke generation portion of the project, we used the character rnn demoed earlier in the class, modified with the addition of two additonal RNN layers and trained it on a collection of jokes found on Kaggle and one liners scraped from Reddit. We then fed the generated jokes into the TacoTron/Waveglow example for text to speech and generated a .wav file. After this we stiched on a generated laughing sound at the end of the joke to complete the joke. The laughter was generated using the wavenet model and was trained using a dataset of wav files found in Kaggle. The jokes that the neural net makes aren't entirely exactly coherent, but they do have comedic value and sometimes elicit laughter. For comedic intents and purposes, being able to make people laugh should be considered a success, even if it can't generate a decent pun. Experimenting with different temperatures, we found that it could be rather prone to reguritaging jokes at anything below 0.8 and had to keep it high. We had originally wanted to fully automate the process of generating spoken jokes combining them with the laughter. Unfortunatley we ran into some trouble exporting the .wav files and ended up partially doing the process manually.  Future directons that we could take the project are Alexa skills or an "easy button" like contraption. 


## Model/Data

Briefly describe the files that are included with your repository:
- oneliners.tsv, jokes scraped from reddit (r/oneliners) 
- jokes.csv, questiona and answer two-liner joke repository (https://www.kaggle.com/jiriroz/qa-jokes)
- all_laughs - all the laughter samples from the dataset we found
- verified_laughs - laughter samples from the same dataset that were labelled to contain laughter sounds by a human
laughter data source: https://www.kaggle.com/c/freesound-audio-tagging/data


## Code

Your code for generating your project:
- CharRNN:
  -char_rnn_QA.ipynb and char_rnn_onliners.ipynb, these files almost the same and are based on the character rnn example in project 1.
- Tacotron2:
  -tacotron_waveglow_tts.ipynb, this file is based upon the tacotron2 tts example code with an additional text cleaning function.
- Jupyter notebooks: 
  - PRAW Scraping.ipynb, this file is used for scraping the "top" 1000 posts from a specific subreddit
- wavenet is already implemented in here: https://github.com/ibab/tensorflow-wavenet, so commands only need to be ran on the terminal.
- To run our model for the laughter, the /logdir directory should be copied into the wavenet folder (after wavenet is up and running). Then by running generate.py + arguments a .wav file is generated.
- laughdata_management -  scripts/notebooks for managing the input data from the sounds dataset
- combining_joke_laugh.ipynb - notebook that automates the process of combining generated jokes with generated laughter.

## Results

Documentation of your results in an appropriate format, both links to files and a brief description of their contents:
- Our results are in a .wav file format, put together like a stand-up comic's set (a really bad standup comic)
- These are found in the /stitched directory.


## Technical Notes

Any implementation details or notes we need to repeat your work. 
- Does this code require other pip packages, software, etc?
  The Reddit scraping portion of the code requires praw and pandas, otherwise the code should run on packages already included and used in example code.
- The computer laughter generation requires running a wavenet implementation (https://github.com/ibab/tensorflow-wavenet).
- In addition, a few scripts and notebooks were used for cleaning and fixing input data and results.
- Our code only runs on datahub.

## Reference

References to any papers, techniques, repositories you used:
- Repositories:

https://github.com/ibab/tensorflow-wavenet

As well as the ones included in the class repository

- Blog posts:

https://deepmind.com/blog/wavenet-generative-model-raw-audio/

https://www.kaggle.com/jiriroz/qa-jokes

https://www.kaggle.com/c/freesound-audio-tagging/data
