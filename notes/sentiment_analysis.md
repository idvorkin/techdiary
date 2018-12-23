## Success Critera

- Deeper understanding of what I care about.
- Played with different cloud stacks for NLP
- Do  simple work frequency analysis
- Played with word embeddings
- Topic/mood over time visualization.
- use the new dotnet core from WSL and *nix

## Abstract

At my best, I do daily sstream of conciousnes jounralling . These journal entries should have insights I can apply to my life. I'm too lazy to read the journal entries, but it's a great corpus to see how I can use NLP and ML tech on myself.

This gives me an excuse to use NLP services, and play with them.


## Tasks

### Convert exported 750words data to per day files

I used a service called 750words to do daily stream of conciousness journally. I have several years of data in this format, and I want to convert to the format I'm using now. this will be a good corpus for anlaysis.


### Call Google NLP from C sharp

I'm feeling adventurous, and want to learn C# from dotnet core as well.
https://github.com/idvorkin/play-google-nlp


#### Get credentials.

1. Create creds from google console.
1. make server creds , generates a .json you need to store locally.
1. Point GOOGLE_APPLICATION_CREDENTIALS to your downloaded creds

    ```export GOOGLE_APPLICATION_CREDENTIALS=~/google-nlp/igorplaygocreds.json```

1. That's the normal way, but I want to share code between win and WSL so had to add setting environment to my c# code.

PROS:

- OMG - I forgot how awesome VS on C# is. Even without resharper, it's just a dream to use. code completion for everything. Debugging just works.


CONS:

- I'm a bit crazy and wanted to use C# from both visual studio and from WSL.
- VS builds isn't compatible with how WSL builds, and if you build from WSL, you lose code completion in VS.
- To be able to edit in VS, and run from VS, I had to
- Work around create a seperate repo for the WSL side, and override files with symlinks to the windows side, this lets me edit in VS, and run from WSL, after I rebuild.
- Setting credentials consistely in C# in both Windows/WSL is painful so I did the work in code. Ugg


### Put google NLP output into pandas

### Evaluate NLP Solutions from various vendors

#### Google NLP

The place I decided to start.

#### AWS Comprend

#### IBM watson.

#### Azure NLP service

Limited, only supports extraction of key topics, without the different spots of them.

## Use cases - Functional

#### I can see what I'm thinking about on a single day.
#### I can see what I'm thinking about over a time period.
#### I can see when my mood goes south.


## Up next

## Notes

