AUTOMATED TOPIC DETECTION AND TRACKING
======================================
For News Articles
-----------------

### Team Members
| Name                           | Git Account URL                    |
|--------------------------------|-------------------------------------
| Dinesh Pandarinathan Subramani | https://github.com/dineshpsubramani|
| Vibha Dharmendra Bhambani      |  |
| Shakshi Maheswari              | https://github.com/shakshimaheshwari|
| Sharanya Vishnampettai Raju    | |


#Introduction
  News is an important information source. Detecting the occurrences of new events and tracking the processes of the events are important for decision-making in this fast-changing network era. This project aims to accomplish this in Tamil language.

###Problem Statement:
The project aims at automatically identifying and classifying streams of similar news articles. It solves the problems of both detection and tracking based on the well-known IDF - weighted cosine coefficient similarity metric. 

  Topic Detection and Tracking (TDT) has been implemented for languages like English, Chinese and Arabic but not in Tamil. It will be a huge leap for Tamil Media to automatically publish related news articles.
  
#Method
###Materials:
  * A corpus that is constructed by obtaining various news articles from Tamil news websites and annotating each article with certain topics manually.
  * EMILLE Monolingual Corpus in Tamil that contains news articles from “Dinakaran” that includes news events like cinema, general news, politics, sports, etc..

###Procedure:
  Our approach to all TDT tasks was based on the vector-space model. 

  1. **Topic tracking:** We are given a small number, Nt, of training stories that discusses a particular topic. The objective is to identify subsequent mentions of the same topic in a news stream.
    * **Topic Representation:** We represent the topic as a point in the same vector space as Tamil documents. To compute the topic vector T, we sum the vector representations D of each- pseudo document in the training set Th.
Story-Topic Similarity: We use cosine coefficient to measure the similarity of a given new story to the topic representation. 
    * **TF-IDF Word Weighting:** The story consists of ‘tf’ and ‘idf’ components calculated for each word
Collection-wide Statistics: We compute incremental document frequency, involving just the documents that precede the current document Dk in the stream. 
    * **Score normalization:** We normalize the cosine similarity scores in order to make them comparable.
    * **Thresholding:** We use a single global threshold for all the topics being tracked.
  2. **Topic Detection:** Topic detection can be accomplished using any clustering algorithm that satisfies the two restrictions:
    * **Clustering has to be done on the fly:** we have to decide on a cluster for story Dk before we are allowed to examine the next story Dk+1.
    * Resulting clusters must be non overlapping i.e. every story must belong to one and only one cluster.

#Evaluation
* **Misses and False Alarms:** During the evaluation, these decisions are compared to ground truth-decisions made by a group of human annotators.
* **TDT Cost Function-TDT:** Researchers evolved the following cost function that takes into account prior probabilities of each error type along with the associated costs for missing an event or making a false alarm
* **Detection Error Tradeoff Curves:**  A DET curve also allows us to measure system performance independent of the threshold selection.
The Baseline System for Comparison is TDT 2002 in English, Chinese, and Arabic.

#References
1. ALLAN, J. 2002a. Introduction to topic detection and tracking. In *Topic Detection and Tracking: Event-based Information Organization*, J. Allan, ed. Kluwer Academic Boston, MA, 1–16
2. FISCUS, J. G. AND DODDINGTON, G. R. 2002. Topic detection and tracking evaluation overview. In *Topic Detection and Tracking: Event-based Information Organization*, J. Allan, ed. Kluwer Academic, Boston, MA, 17–31
