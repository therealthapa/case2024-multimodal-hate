# Task 4 - Shared task on Multimodal Hate Speech Event Detection at [CASE 2024](https://emw.ku.edu.tr/case-2024/) #

Hate speech detection is one of the most important aspects of event identification during political events like invasions. In the case of hate speech detection, the event is the occurrence of hate speech, the entity is the target of the hate speech, and the relationship is the connection between the two. Since multimodal content is widely prevalent across the internet, the detection of hate speech in text-embedded images is very important. Given a text-embedded image in the context of the Russia-Ukraine crisis, this task aims to automatically identify hate speech and its targets. This task will have two subtasks (i) Hate speech identification (ii) Targets of Hate Speech Identification. This is an ongoing challenge that was held in [CASE 2023](https://emw.ku.edu.tr/case-2023/) as well.

## Sub-task A ##
<b> Hate Speech Detection:</b> The goal of this task is to identify whether the given text-embedded image contains hate speech or not. The text-embedded images, which are the dataset for this subtask, will have annotations for the prevalence of hate speech.

The dataset for this sub-task has two labels viz. "Hate Speech" and "No Hate Speech".

## Sub-task B ##
<b> Target Detection:</b> The goal of this subtask is to identify the targets of hate speech in a given hateful text-embedded image. The text-embedded images are annotated for "community", "individual" and "organization" targets.

To know more about the dataset, please refer to our [paper](https://openaccess.thecvf.com/content/CVPR2023W/MMCM/html/Bhandari_CrisisHateMM_Multimodal_Analysis_of_Directed_and_Undirected_Hate_Speech_in_CVPRW_2023_paper.html).
The sample codes for both the subtasks are provided in the repo. 


## Participation ##

Join our codalab competition [here](https://codalab.lisn.upsaclay.fr/competitions/16203).

Training data is provided at: https://drive.google.com/drive/folders/173EJjsNblxhjACXzIWardUqCcSYtcJh0

Evaluation/Validation data is provided at: https://drive.google.com/drive/folders/1LL2OD7v2GhrmeC0j2Gm9YFCOa5vobVjc

A link for testing data will be provided to all the registered participants on November 30, 2023. 

## Dataset ## 
All the images have a unique identifier called "index". The labels for training data are organized in the folder provided. For evaluation and testing, the submission format is mentioned below.

## Instructions for OCR Extraction ##
If you want to extract OCR, you can use Google Vision API, tesseract, etc. In the paper that benchmarks this dataset, we have used Google Vision API to extract OCR for training the models. The code can be found [here](https://github.com/therealthapa/case2024-multimodal-hate/tree/main/Extracted%20Text).

A lot of participants do not have access to vision API. They can use the extracted text from [here]().

## Evaluation ## 

The results are only accepted in codalab. The submission will be evaluated with a f1-score.

The script takes one prediction file as the input. Your submission file must be a JSON file which is then zipped. We will only take the first file in the zip folder, so do not zip multiple files together. 

<b>IMPORTANT:</b> The index (image name) in json should be in ascending order.

For subtask A, the final prediction submissions should be like the following. Make sure that your hate label is given as "1" and non-hate label is given as "0".

```python
{"index": 23568, "prediction": 1}
{"index": 45865, "prediction": 0}
{"index": 98452, "prediction": 1}
```

Similarly, for the subtask B, the final prediction submissions should be like the following. Make sure that your individual, community, and organization labels are given as "0", "1", and "2" respectively.

```python
{"index": 23568, "prediction": 1}
{"index": 36987, "prediction": 2}
{"index": 45865, "prediction": 0}
```
<b>IMPORTANT:</b> The index (image name) in json should be in ascending order.

## Publication ##

Participants in the Shared Task are expected to submit a paper to the workshop. Submitting a paper is not mandatory for participating in the Shared Task. Papers must follow the CASE 2023 workshop submission instructions and will undergo regular peer review. Their acceptance will not depend on the results obtained in the shared task but on the quality of the paper. Authors of accepted papers will be informed about the evaluation results of their systems prior to the paper submission deadline (see the important dates). All the accepted papers will be published in ACL Anthology.

## Invitation for Special Issue ##
Top-performing teams and best models will be invited for a special issue in journals (T.B.D.).

## Timeline of the Events ##
<ul>

<li>Training & Evaluation data available: Nov 1, 2023 </li>

<li>Test data available: Nov 30, 2023 </li>

<li>Test start: Nov 30, 2023 </li>

<li>Test end: Jan 5, 2024 </li>

<li>System Description Paper submissions due: Jan 12, 2024 </li>

<li>Notification to authors after review: Jan 26, 2024 </li>

<li>Camera ready: Jan 30, 2024 </li>

<li>CASE Workshop: 21-22 Mar, 2024 </li>
</ul>


## Organizers ##
<ul>
<li> Surendrabikram Thapa (Virginia Tech, USA) </li>
<li> Farhan Ahmad Jafri (Jamia Millia Islamia, India) </li>
<li> Ali Hürriyetoğlu (KNAW Humanities Cluster DHLab, Netherlands) </li>
<li> Hariram Veeramani (UCLA, USA) </li>
<li> Kritesh Rauniyar (Delhi Technological University, India) </li>
<li> Usman Naseem (James Cook University, Australia) </li>
</ul>

## Contact ##
If there are any questions related to the competition, please contact surendrabikram@vt.edu


## References ##

If you use the dataset, please cite it as follows:

```bibtex
@inproceedings{bhandari2023crisishatemm,
  title={CrisisHateMM: Multimodal Analysis of Directed and Undirected Hate Speech in Text-Embedded Images From Russia-Ukraine Conflict},
  author={Bhandari, Aashish and Shah, Siddhant B and Thapa, Surendrabikram and Naseem, Usman and Nasim, Mehwish},
  booktitle={Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition (CVPR) Workshops},
  pages={1993--2002},
  year={2023}
}
```

All the papers submitted as shared task reports should cite the shared task as follows:

```bibtex
@inproceedings{thapa2023multimodal,
  title={ Multimodal Hate Speech Event Detection - Shared Task 4, CASE 2023},
  author={Thapa, Surendrabikram and Jafri, Farhan Ahmad and H{\"u}rriyeto{\u{g}}lu, Ali and Vargas, Francielle and Lee, Roy Ka-Wei and Naseem, Usman},
  booktitle={Proceedings of the 6th Workshop on Challenges and Applications of Automated Extraction of Socio-political Events from Text (CASE)},
  year={2023}
}
```
