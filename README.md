# AudioGPT
Testing AKs nano GPT on Audio

The purpose of this repo is for exploration and testing. (this is not a fully finished repo, and WIP) 

This method isn't descbribed anywhere, it's literally just me slapping data into a transformer and seeing if I can get it learn. 

I got to overfit through an unadvised method, which is having no dropout and having the same data for train and eval. No split. 

The reason for attempting to overfit, was this would highlight that the model could remake the audio data. 

Was very hard to train with dropout @0.3 or 0.5, and train/val splits of 90/10, and 80/20, and 50/50 were tried; 
with single drum loop this proved challenging. With a larger dataset of ~2m tokens @ 50k steps and constantly tweaking LR I stil couldn't get a great improvement. I think transformers need to be trained with not only large datasets, but for a long amount of time (which costs money, and colab ain't gonna cut it I don't think). 

Future explorations will be using Hugging face's transformer library, with Blurr and Fastxtend/Fast Ai or Mosaic. Mixed P, fused optimisers and torch compile should give some training increases. 

I'll do some other tests, making tokenisers for audio, sentence piece, specific for BERT, and Unigram (t5 models). I'd like to shift my attention to BERT models, and potentially fine tuning a BERT/DistilBERT model to generate audio. 
