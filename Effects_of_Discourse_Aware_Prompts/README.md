# Effects of Discourse Aware Prompts

### **Catalog** 

    .
    ├── Base                       # Sentence-level baseline system using InstructGPT API without any context-based chat box
    │   ├── Fiction                # tokenized and BPEed testset
    │   │   ├── *.format_1.zh      # original/oracle testset for sent-level
    │   │   ├── *.format_1.en      # original/oracle testset for doc-level
    │   ├── News                   # raw testset for each domain
    ├── P1              # Our evaluation metric
    │   ├── aZPT                   # evaluation toolkit
    │   ├── aZPT_output            # output files in details of aZPT
    │   ├── human_score            # human judgements on 6 systems
    │   ├── scirpts                # scripts for getting alignment
    ├── P2       # Bechmark related resources
    │   ├── mt                     # Machine translation task
    │   │   ├── data               # training data for MT baseline
    │   │   │   ├── FT_dataset     # domain-specific data for QA Forum and Web Fiction
    │   │   │   ├── Movie_Subtitle # training data for Movie_Subtitle
    │   │   │   ├── WMT2021        # training data for Others
    │   │   ├── code               # training code
    │   │   ├── model              # comparative models  
    │   ├── zpr                    # Zero pronoun recovery task
    │   │   ├── data               # training data for zpr
    │   │   │   ├── Movie_Subtitle # domain-specific data for Movie Subtitle
    │   │   │   ├── QA_Forum       # domain-specific data for QA Forum
    │   │   │   ├── Others         # training data for Others
    │   │   ├── scirpt             # Make training data from raw
    │   │   ├── code               # training codes for zpr task
    │   │   ├── model              # comparative_models  
    │   └── zpt                    # Zero pronoun translation task
    │   │   ├── context-aware      # Doc-level MT
    │   │   │   ├── scirpt         # make doc-level data
    │   │   │   ├── model          # comparative_models  
    │   │   │   ├── codes          # training codes for doc-level mt
    │   │   ├── reconstructor      # Reconstructor
    │   │   │   ├── scirpt         # make training data
    │   │   │   ├── model          # comparative_models  
    │   │   │   ├── codes          # training codes for reconstructor