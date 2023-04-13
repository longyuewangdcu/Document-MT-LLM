# Effects of Discourse Aware Prompts

Datasets and Experimental Results in [Effects of Discourse Aware Prompts].

### **Dataset Catalog** 

We investigated three representative prompts. We utilize P1 to translate the document sentence by sentence, with each sentence placed in a single conversational turn and the entire document contained within one chat box. This mainly takes advantage of ChatGPT's long-term modeling ability in the chat box. P2 and P3 combine multiple continuous sentences and translate them in one conversational turn until the entire document is finished. This aims to maximize the context modeling in one conversational turn. The only difference is whether or not the sentential boundary tag "[]" is inserted into each sentence. 

<p align="center">
    <img src="./img/prompts.png" width="50%">
</p>

We release related datasets and translation outputs as follows, which is linked to [Experimental Results].

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



![](./img/prompts.png)
![](./img/prompts_results.png)

### **Contact information**

Wang, Longyue : vinnylywang@tencent.com