# JUSThink Dialogue and Actions Corpus (Dataset)

[![DOI](https://zenodo.org/badge/344263661.svg)](https://zenodo.org/badge/latestdoi/344263661)
[![CC BY 4.0][cc-by-shield]][cc-by]

The information contained in this dataset (JUSThink Dialogue and Actions Corpus) includes dialogue transcripts, event logs, and test responses of children aged 9 through 12, as they participate in a robot-mediated human-human collaborative learning activity named JUSThink, where children in teams of two solve a problem on graphs together. 
The information was collected in a study at two international schools in Switzerland, in October 2019.
The JUSThink activity and its study is first described in [[1]](#references), and elaborated with findings concerning the link between children's learning, performance in the activity, and perception of self, the other and the robot in [[2]](#references).
See the [project website](https://www.epfl.ch/labs/chili/index-html/research/animatas/justhink/) for details.

This data has been studied in [[3]](#references) to automatically analyse how participants' align their use of task-specific referents in their dialogue and actions, and how it relates to the task success (i.e. their task performance and learning outcomes): these tools are available from the Zenodo Repository, DOI: [10.5281/zenodo.4675070](http://doi.org/10.5281/zenodo.4675070).


### Publications

If you use this work in an academic context, please cite the following publications:
        
* Norman*, U., Dinkar*, T., Bruno, B., & Clavel, C. (2022). Studying Alignment in a Collaborative Learning Activity via Automatic Methods: The Link Between What We Say and Do. Dialogue & Discourse, 13(2), 1–48. https://doi.org/10.5210/dad.2022.201

        @article{norman_dinkar_studying_2022,
            title        = {Studying Alignment in a Collaborative Learning Activity via Automatic Methods: The Link Between What We Say and Do},
            author       = {Norman*, Utku and Dinkar*, Tanvi and Bruno, Barbara and Clavel, Chloé},
            journaltitle = {Dialogue \& Discourse},
            volume       = {13},
            number       = {2},
            pages        = {1--48},  
            month        = aug,
            year         = 2022,
            doi          = {10.5210/dad.2022.201},
            note         = {*Contributed equally to this work.},
        }
        
* Nasir*, J., Norman*, U., Bruno, B., & Dillenbourg, P. (2020). When Positive Perception of the Robot Has No Effect on Learning. 2020 29th IEEE International Conference on Robot and Human Interactive Communication (RO-MAN), 313–320. https://doi.org/10.1109/RO-MAN47096.2020.9223343

        @inproceedings{nasir_norman_when_2020,
            title        = {When Positive Perception of the Robot Has No Effect on Learning},
            author       = {Nasir*, J. and Norman*, U. and Bruno, B. and Dillenbourg, P.},
            pages        = {313--320},
            booktitle    = {2020 29th {IEEE} International Conference on Robot and Human Interactive Communication ({RO}-{MAN})},
            year         = 2020,
            month        = aug,
            doi          = {10.1109/RO-MAN47096.2020.9223343},
            note         = {*Contributed equally to this work.},
        }

* Norman, Utku, Dinkar, Tanvi, Nasir, Jauwairia, Bruno, Barbara, Clavel, Chloé, & Dillenbourg, Pierre. (2021). JUSThink Dialogue and Actions Corpus [Data set]. In Dialogue & Discourse (v1.0.0, Vol. 13, Number 2, pp. 1–48). Zenodo. https://doi.org/10.5281/zenodo.4627104.

        @software{norman_dinkar_justhink_dataset_2021,
            title        = {JUSThink Dialogue and Actions Corpus},
            author       = {Norman, Utku and Dinkar, Tanvi and Nasir, Jauwairia and Bruno, Barbara and Clavel, Chloé and Dillenbourg, Pierre},
            month        = mar,
            year         = 2021,
            publisher    = {Zenodo},
            version      = {v1.0.0},
            doi          = {10.5281/zenodo.4627104},
            url          = {https://doi.org/10.5281/zenodo.4627104},
        }



1. [Content](#code_description)
    1. [Transcripts](#transcript_content)
    2. [Logs](#log_content)
    3. [Test Responses](#test_content)
2. [Acknowledgements](#acknowledgements)
3. [References](#references)


## 1. Content <a name="code_description"></a>

JUSThink Dialogue and Actions Corpus is consisted of three parts:

1. [transcripts](transcripts): anonymised dialogue transcripts for 10 teams of two children (see [1.1. Transcripts](#transcript_content))
2. [logs](logs): anonymised event logs for 39 teams (see [1.2. Logs](#log_content) for details)
3. [test responses](test_responses): pre-test and post-test responses for 39 teams, and the key i.e. the correct responses (see [1.3. Test Responses](#test_content))

In addition, there is metadata that contains information on the network that the children have worked on:
It is a JSON file in a node-link format, providing the node labels (e.g. "Mount Luzern"), node ids, x, y position of a node, edges between the nodes, and edge costs ([metadata/network.json](metadata/network.json)).
It can be [read](https://networkx.org/documentation/stable/reference/readwrite/generated/networkx.readwrite.json_graph.node_link_graph.html) into a [NetworkX](https://networkx.org/) graph.


### 1.1. Transcripts <a name="transcript_content"></a>
This part of the dataset contains the anonymised dialogue transcripts for 10 teams of two children (out of 39 teams).

It consists of 10 files, with one tab-separated text file per team ([transcripts/justhink19_transcript_<team_no\>.csv](transcripts/)).

In particular, the columns are:

* *team_no*: The number of the team that the dialogue belongs to
* *utterance_no*: The number of the utterance, starting from 0
* *start*: The start timestamp of the utterance (in seconds), from the beginning of the activity
* *end*: The end timestamp of the utterance (in seconds)
* *interlocutor*: The person (or the robot) that is speaking (*A*, *B*: the participants; *R*: the robot; *I*: an experimenter)
* *utterance*: The content of the utterance

Utterance segmentation is based on [[4]](#references)'s definition of an *Inter Pausal Unit (IPU)*, defined as "a stretch of a single interlocutor's speech bounded by pauses longer than 100 ms". 
We also annotated punctuation markers, such as commas, full stops, exclamation points and question marks, fillers, such as 'uh' and 'um', and the discourse marker 'oh'.
Transcription included incomplete elements, such as "Mount Neuchat-" in "Mount Neuchat- um Mount Interlaken".
We standardised variations of pronunciation in the transcriptions, and we do not account for e.g. variations in accent.
For anonymisation, a person's name is replaced with a pseudonym (in particular Ann for participant *A*, Bob for participant *B*, and other pesudonyms if an interlocutor refers to someone else).
The numbers that are explicitly referring to the cost of an edge or a set of edges are written as numerals.
A graduate student completed two passes on each transcript, and then were checked by another native English speaking graduate student with experience in transcription/annotation tasks.

Note that the start and end times are synchronised with the log times, and the robot's introductory line to start the activity ("so, Ann and Bob, let's start building the tracks. ...", available in the [logs](#log_content)) is not included in the transcripts. In addition, some of the utterances by the experimenter (*I*) and the robot (*R*) are omitted from the transcripts; these are indicated with "..." in the utterance content. All of the utterances by the robot are available in the logs in complete form.


### 1.2. Logs <a name="log_content"></a>
This part of the dataset contains anonymised event log data for 39 teams of two children.

It consists of 39 files, with one tab-separated text file per team ([logs/justhink19_log_<team_no\>.csv](logs/)).

In particular, the columns are:

* *team_no*: The number of the team that the event belongs to
* *attempt_no*: The attempt number that the event belongs to, starting from 1. An attempt is the duration of the team constructing a solution and submitting it together.
* *turn_no*: The turn number of the event, starting from 1. A turn is the duration where one of the participants is in the figurative view, and the other is in the abstract view (see [[2]](#references) for a description of the views).
* *event_no*: The event number of the event, starting from 1
* *time*: The logging timestamp of the event, from the beginning of the activity (in seconds)
* *subject*: The subject that the event is executed by (*A*, *B*: the participants; *R*: the robot; *T*: the team)
* *verb*: The verb that describes the event (e.g. "presses", "adds", "removes")
* *object*: The object that is acted on by the subject performing the verb (e.g. "submit (enabled)" for subject i.e. participant: *A*, verb i.e. the action: "presses")

For example, in a logged event "A presses submit (disabled)", submit refers to the submit button, and "enabled" is the status of the button at the time of the button press by participant *A* (that it was active/enabled), and hence the help window is displayed afterwards.
Note that the closing of e.g. the help window is not logged.
An event "B presses submit (disabled)" is logged, when *B* tries to submit a solution, by pressing the submit button, while it was not allowed to submit, i.e. the current solution was not connecting all nodes to each other (see [[2]](#references) for the activity details).

Regarding the collaborative modification and submission of a solution, e.g. an event "B adds Zurich-Gallen (2-8)" modifies the team's current solution by connecting Zurich to Gallen, where 2 and 8 correspond to the node ids respectively.
An event "T submits	cost=64 (opt_cost=22)" indicates that the team's solution is registered as a solution by both of the participants pressing their respective submit buttons; where the total cost of the submitted solution is 64, whereas the optimal cost (for a correct i.e. optimal solution) is 22.
Note that in a few cases a team's submit event might not reflect the total cost by counting the add (and subtracting remove) events due to an error in the logging; however, the submitted solution's cost (as logged in an event "T submits ...") is always correct, and this is what the robot reacts to (by giving feedback on the solution, see [[2]](#references)).

For anonymisation, the robot's introductory line to start the activity ("so, Ann and Bob, let's start building the tracks. ...") has the participant *A*'s name replaced with Ann (and *B* with Bob), while within the activity the robot pronounces the names of children.


### 1.3. Test Responses <a name="test_content"></a>
This part of the dataset contains the responses of each participant in each team to the pre-test and post-test for 39 teams.
Each test contains 10 multiple-choice (single answer) questions (i.e. items) with 3 options (recorded as 0, 1 or 2), and assesses a concept on spanning trees (see [[2]](#references) for details).

It consists of 2 files:

* one comma-separated text file for the pre-test responses ([test_responses/justhink19_pretest.csv](test_responses/justhink19_pretest.csv)), and
* one comma-separated text file for the post-test responses ([test_responses/justhink19_posttest.csv](test_responses/justhink19_posttest.csv)).

In particular, the columns are:

* *team_no*: The number of the team, or "key" for the correct responses
* *q?\_A*: The response of participant *A* to a particular item (among 10 items indexed from 1 to 10)
* *q?\_B*: The response of participant *B* to a particular item


## Acknowledgements
 This project has received funding from the European Union's Horizon 2020 research and innovation programme under grant agreement No 765955. Namely, the [ANIMATAS Project](https://www.animatas.eu/).


## License <a name="license"></a>
This work is licensed under a [Creative Commons Attribution 4.0 International License][cc-by].

[![CC BY 4.0][cc-by-image]][cc-by]


## References <a name="references"></a>
[1] J. Nasir, U. Norman, B. Bruno, and P. Dillenbourg, “You Tell, I Do, and We Swap until we Connect All the Gold Mines!,” ERCIM News, vol. 2020, no. 120, 2020, [Online]. Available: [https://ercim-news.ercim.eu/en120/special/you-tell-i-do-and-we-swap-until-we-connect-all-the-gold-mines](https://ercim-news.ercim.eu/en120/special/you-tell-i-do-and-we-swap-until-we-connect-all-the-gold-mines).

[2] J. Nasir\*, U. Norman\*, B. Bruno, and P. Dillenbourg, “When Positive Perception of the Robot Has No Effect on Learning,” in 2020 29th IEEE International Conference on Robot and Human Interactive Communication (RO-MAN), Aug. 2020, pp. 313–320, doi: [10.1109/RO-MAN47096.2020.9223343](https://doi.org/10.1109/RO-MAN47096.2020.9223343).

[3] U. Norman\*, T. Dinkar\*, B. Bruno, and C. Clavel, "Studying Alignment in a Collaborative Learning Activity via Automatic Methods: The Link Between What We Say and Do," Dialogue & Discourse, 13(2), 1–48. [10.5210/dad.2022.201](https://doi.org/10.5210/dad.2022.201).

[4] H. Koiso, Y. Horiuchi, S. Tutiya, A. Ichikawa, and Y. Den, “An analysis of turn-taking and backchannels based on prosodic and syntactic features in Japanese map task dialogs,” Language and speech, vol. 41, no. 3–4, pp. 295–321, 1998, doi: [10.1177/002383099804100404](https://doi.org/10.1177/002383099804100404).



[cc-by]: http://creativecommons.org/licenses/by/4.0/
[cc-by-image]: https://i.creativecommons.org/l/by/4.0/88x31.png
[cc-by-shield]: https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg
