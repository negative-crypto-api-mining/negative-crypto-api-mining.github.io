## Welcome to The Artifacts Page

This is the page to share the artifacts related to the paper "Negative Results on Mining Crypto-API Usage Rules in Android Apps".

### Abstract of the Paper

Android app developers recurrently use crypto-APIs to provide data security to app users.
Unfortunately, misuse of APIs only creates an illusion of security and even exposes apps to systematic attacks.
It is thus necessary to provide developers with a statically-enforceable list of specifications of crypto-API usage rules.
On the one hand, such rules cannot be manually written as the process does not scale to all available APIs.
On the other hand, a classical mining approach based on common usage patterns is not relevant in Android,
given that a large share of usages include mistakes.
In this work, building on the assumption that “developers update API usage instances to fix misuses”,
we propose to mine a large dataset of updates within about 40 000 real-world app lineages to infer API usage rules.
Eventually, our investigations yield negative results on our assumption that API usage updates tend to correct misuses.
Actually, it appears that updates that fix misuses may be unintentional:
the same misuses
patterns are quickly re-introduced by subsequent updates.

### App Lineages

An app lineage is defined as the consecutive series of its versions (i.e., APKs).
Since the updates of Android apps is the main subject of this study,
we constructed our own app lineages based on the apps from [Androzoo](https://androzoo.uni.lu)
and used the procedure proposed by Gao et al. in their [paper](https://dl.acm.org/citation.cfm?id=3183440.3194968).
After certain steps of data cleaning, the final lineage dataset used in this
study contains 39,213 app lineages (i.e., 598,875 apks).
The list of the lineages is shared [here](resources/final_lineages).

### Metadata

Part of this study requires up-to-date metadata of Android apps.
Therefore, we crawled these information from GooglePlay.
As certain constraints are implemented by GooglePlay, we were only able to collect metadata for
around 60% of the lineages.
The metadata include category, rate, installs and the file can be downloaded
[here](resources/app_rate.csv)

### _CogniCrypt_ Reports

_CogniCrypt_ is a static analyzer framework for detecting JCA API misuses
in Java programs and it provided an Android app specified analyzer which
is used in this study.
It can be accessed from their [github site](https://github.com/CROSSINGTUD/CryptoAnalysis-Android).
Meanwhile, the reports generated in this study is available [here](data/sample).
(Note: because of the large size of these reports, it will be share with a link
to our own server. Therefore, during double blind review period, the link will not
be revealed and only one sample report is provided.)

### Common Libraries

In this study, we investigated crypto-API updates from different aspects including
library code.
We adopted the method proposed by Li et al. in their [paper](https://ieeexplore.ieee.org/document/7476661/)
to build an Android library whitelist of our own.
Relevant result in this paper is based on this list and it can be downloaded
[here](resources/commen_lib_list.csv)

### JCA APIs

The crypto-API studied in this paper is Java Cryptography Architecture (JCA)
APIs, which is the widest used in Java programs as well as Android apps so far.
Although, the misuses of crypto-API is the main focus, relevant usages are
necessary to know to distinguish a misuse fixing from usage removing.
As misuse analyzer (i.e., _CogniCrypt_) provides mainly misuses information,
we developed our own tool based on _Soot_ and extracted crypto-API usage
information of the dataset.
All the usage information are store in one JSON file and can be download
[here]()
(Note: because of the large size of the file, it will be share with a link
to our own server. Thus, during double blind review period, the link will not
be revealed.)
