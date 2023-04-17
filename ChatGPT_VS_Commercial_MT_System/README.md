# Effects of Discourse Aware Prompts

Datasets and Experimental Results in [ChatGPT vs. Commercial Systems].

### **Dataset Details** 

We compare ChatGPT/GPT-4 with three commercial translation products, including Google Translate, DeepL Translate, and Tencent TranSmart.

We investigate three representative prompts via ChaGPT. We utilize P1 to translate the document sentence by sentence, with each sentence placed in a single conversational turn and the entire document contained within one chat box. This mainly takes advantage of ChatGPT's long-term modeling ability in the chat box. P2 and P3 combine multiple continuous sentences and translate them in one conversational turn until the entire document is finished. This aims to maximize the context modeling in one conversational turn. The only difference is whether or not the sentential boundary tag "[]" is inserted into each sentence. 

<p align="center">
    <img src="./img/prompts.png" width="40%">
</p>

Accordingly, we release the Chinese-English datasets in News and Fiction domains. 

<p align="center">
    <img src="./img/data.png" width="60%">
</p>

The catalog (including input with prompts, translation outputs and reference) is as follows.

    .
    ├── Base                       # Sentence-level baseline using InstructGPT API without any context-based chat box
    │   ├── Fiction                # mZPRT Fiction
    │   │   ├── *.format_1.zh      # Input formated into Prompt 1
    │   │   ├── *.format_1.en      # Translation output
    │   ├── News                   # WMT2022 News
    │   │   ├── *.format_1.zh      # Input formated into Prompt 1
    │   │   ├── *.format_1.en      # Translation output
    ├── P1                         # ChatGPT output via Prompt 1
    │   ├── Fiction                # mZPRT Fiction
    │   │   ├── *.format_1.zh      # Input formated into Prompt 1
    │   │   ├── *.format_1.en      # Translation output
    │   ├── News                   # WMT2022 News
    │   │   ├── *.format_1.zh      # Input formated into Prompt 1
    │   │   ├── *.format_1.en      # Translation output
    ├── P2                         # Combine multiple continuous sentences and translate them in one conversational turn until the entire document is finished with boundary tag “[]”.
    │   ├── Fiction                # mZPRT Fiction
    │   │   ├── *.format_2.zh      # Input formated into Prompt 2
    │   │   ├── *.format_2.en      # Translation output (post-processed into sentence level without boundary tag)
    │   ├── News                   # WMT2022 News
    │   │   ├── *.format_2.zh      # Input formated into Prompt 2
    │   │   ├── *.format_2.en      # Translation output (post-processed into sentence level without boundary tag)
    ├── P3                         # Combine multiple continuous sentences and translate them in one conversational turn until the entire document is finished without boundary tag “[]”.
    │   ├── Fiction                # mZPRT Fiction
    │   │   ├── *.format_3.zh      # Input formated into Prompt 3
    │   │   ├── *.format_3.en      # Translation output (post-processed into sentence level)
    │   ├── News                   # WMT2022 News
    │   │   ├── *.format_3.zh      # Input formated into Prompt 3
    │   │   ├── *.format_3.en      # Translation output (post-processed into sentence level)
    ├── Orignal_Dataset            # Sentence-level baseline using InstructGPT API without any context-based chat box
    │   ├── Fiction                # mZPRT Fiction
    │   │   ├── *.zh               # Input in orignal fomat
    │   │   ├── *.en               # Reference in orignal fomat
    │   ├── News                   # WMT2022 News
    │   │   ├── *.zh               # Input in orignal fomat
    │   │   ├── *.en1              # Reference1 in orignal fomat
    │   │   ├── *.en2              # Reference2 in orignal fomat

### **Experimental Results**

We compare the three candidate prompts via ChatGPT and one sentence-level baseline. We use BLEU and d-BLEU to measure sentence- and document-level translation quality. We also conduct two targeted evaluation metrics to measure specific discourse phenomena: accuracy of zero pronoun translation (aZPT) and consistency of terminology translation (cTT).

<p align="center">
    <img src="./img/prompts_results.png" width="90%">
</p>

### **Contact Information**

Wang, Longyue : vinnylywang@tencent.com