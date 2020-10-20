# Project 6 - D(St)reams of Anomalies

### Scope

The dataset used in this project (linked below) contains a collection of Twitter mentions for the company Apple Inc. From the data's README: "The metric value represents the number of mentions for a given ticker symbol every 5 minutes." Each observation consists of a timestamp and a value. The timestamp is a 5 minute time block, and the value is the number of twitter mentions Apple got during that time block. The purpose of this project is to use anomaly detection to determine any anomalies in the series of twitter mentions. For this dataset, I expect there to be point anomalies (ie single observations that stand out from the rest). For instance, if Apple is releasing a new iPhone, it is possible there will be an inordinate number of Twitter mentions in the 5 minute intervals leading up to and after the release.

### Results

I used Isolation Forest and DBSCAN models to determine any anomalies in the number of Apple twitter mentions. The Isolation Forest results appeared to be too simple, considering all values above a certain threshold to be anomalies. The DBSCAN results were more varied and resulted in fewer anomaly detections. Further, DBSCAN revealed a possible collective anomaly occuring among observations to the far right of the time series plot. The last DBSCAN plot looked similar to the Isolation Forest results.

Please see the Jupyter Notebook for more details and further discussion.

### Data
Datasets obtained from:
1. https://www.kaggle.com/boltzmannbrain/nab?
or
2. https://github.com/numenta/NAB/tree/master/data


### Variable descriptions
Timestamp - represents a 5 minute interval of time <br />
Value- represents the number of mentions for a given ticker symbol every 5 minutes <br />


### References
1. To implement Isolation Forest:
     - https://towardsdatascience.com/anomaly-detection-with-isolation-forest-visualization-23cd75c281e2
     - https://blog.paperspace.com/anomaly-detection-isolation-forest/
2. To implement DBSCAN:
    - https://medium.com/@mohantysandip/a-step-by-step-approach-to-solve-dbscan-algorithms-by-tuning-its-hyper-parameters-93e693a91289
