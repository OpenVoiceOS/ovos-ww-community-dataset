# OVOS-WW-Community-Data
Wake Word training data provided by the OpenVoiceOS/Mycroft Community

## Files
### Directory Structure
```
│   README.md
│   
└───licenses/ # contains license templates and the licenses of submitted files.
│   │   license-template.txt
│   │   license-YYYYMMDD-githubusername.txt
│   │   license-YYYYMMDD-githubusername.txt
│   │   ...
│   
└───not-wake-words/ # samples that are clearly not wake words
│   │
│   │   │ README.md
│   │   │ 
│   └───lang-short/ # the two-character ISO 639-1 language code eg de, en, es, pt, etc.
│   │   │   README.md
│   │   │   metadata.csv # a transcript for the not-wake-word files
│   │   │   notwakeword-lang-uuid.wav
│   │   │   notwakeword-lang-uuid.wav
│   │   │   ...
│   │
│   └───noises/ # samples that are not audible words
│       │
│       └───noise-name/ # dataset subfolder, eg "false_activations", "tv_noise", whatever you like
│           │   README.md 
│           │   metadata.csv # name, brief description of noise
│           │   noise-uuid.wav
│           │   noise-uuid.wav
│           │   ...
│
└───wake-words/
    │
    └───lang-short/ # the two-character ISO 639-1 language code eg de, en, es, pt, etc.
        │
        └───ww-name/ # the wakeword name eg hey-mycroft, computer etc
            │   README.md
            │   wakeword-uuid.wav
            │   wakeword-uuid.wav
            │   ...

```

### File Naming Conventions
Wake word clips should be named using the format of “wakeword-lang-uuid.wav”.  UUID’s can be generated using command line tools on unix systems.  Not wake word clips should be named as “notwakeword-lang-uuid.wav”.  Noise clips would use “noise-uuid.wav”.  The name of the model archive should be in the format of “wakeword-lang-preciseversion-YYYYMMDD-githubusername.tar.gz”.  Licenses should use names like “license-YYYYMMDD-githubusername.txt”

### Audio Clip Conventions
Audio files should be WAV files in little-endian, 16 bit, mono, 16000hz PCM format.  FFMpeg calls this “pcm_s16le”.  Clips for wake words should contain only the wake word and silence of no more than one second before and after.  All clips should be less than or equal to three seconds total length.  

## Contributions

### PR Review Process
1. Verify formatting of files is correct
2. Review the license file for correct contents.  
3. Check that included clips are named correctly, formatted correctly (ie, file $clip), and less than three seconds duration (ie, exiftool -Duration \*.wav | some grep and things)
4. Spot check clips to ensure they are the correct wake word, or that noise, or not wake word speech is contained as appropriate.
5. For submitted models, if you speak the submitted language, test the model. (other stuff about testing model here)
6. If PR looks correct and sounds right, then approve and merge. If not, post a comment indicating what needs to be updated.

## Licensing
We prefer audio clips to be submitted under public domain license.  Other acceptable audio licenses include the Creative Commons BY, BY-SA, BY-NC, BY-NC-SA licenses.  A license template for public domain usage is provided in the Licensing directory.  For pre-trained models, we can accept any of the main seven CC licenses including BY-ND and BY-ND-NC. Submissions using other licenses will need to be reviewed more thoroughly before acceptance.  

All audio should be sourced by the submitter. No copyright material will be accepted. No material from unknown provenance will be accepted.

Contributors to the repo must include a license during submission. They are not required to sign the Mycroft Contributor License Agreement.
