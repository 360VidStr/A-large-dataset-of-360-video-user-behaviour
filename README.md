# A-large-dataset-of-360-video-user-behaviour
This dataset is created as a part of research - viewport-aware dynamic 360 video segment categorization. This is an aggregation of 6 different previously published datasets.

The original datasets contained user head orientations while viewing 360 degree videos using a head mounted streaming device. We extracted this data, and preprocessed to yield a common representation.

This dataset contains user head orientation trajectories for 3791 independant viewings of 88 different 360 degree videos with an average of 45 viewings per video.

The total viewing duration is 514215 seconds. (142 hours 50 minutes 15 seconds)

## Original datasets

| Dataset | Video IDs | Duration | Average #viewings|  sampling rate | Data format | HMD used |
| :---    |     :---: |     ---: | :------:  |  ------   |  :------: | :---:|
| 1 [[1]](#1) | 0-6 | 700s | 50 | ~40Hz | Unit quaternion | Razer OSVR HDK2 |
| 2 [[2]](#2) | 7-16 | 60s | 50 | 30Hz | Yaw, pitch, roll | Oculus DK2 |
| 3 [[3]](#3) | 17-32 | 30s | 61 | ~7-9Hz | Yaw, pitch, roll | Oculus DK2 |
| 4 [[4]](#4) | 33-41 | 164s-655s | 48 | ~9Hz | Unit quaternion | HTC Vive |
| 5 [[5]](#5) | 42-59 | 163s-660s |48| 30Hz | Yaw, pitch | HTC vive |
| 6 [[6]](#6) | 60-87| 60s | 30 | 60Hz | Unit quaternion,<br> spherical vectors | Oculus Go |

The files from dataset 3 are currently unavailable and will be added soon with the permission from the original authors.
All the videos in equiectangular format will be made available soon.

## AggreatedDataset format

The folder AggregatedDataset contains 88 txt files containing the data for each video. 
- The aggregated dataset is sampled at 10Hz. t=[0,0.1,0.2... ]
- Each file is named using the corresponding video ID. Additional information about the videos are given in 'VideoMetadata'
- Every file has 2n+1 lines where n= number of users who watched the video. First line contains the time points of sampling (in seconds).  
- 2i-1 th line has pitch angles for the ith user, 2i th line has the yaw angles for the ith user
- Both yaw and pitch angles are given in radians. (Roll angle was ignored)

The folder ExtractedFeatures contains the calculated features for each user head orientation trajectory chunk of 2s length. The sub folder is names after the chunk duration, and the txt files are named by the corresponding video ID.
The text file contains n lines where n= number of users (viewings). 17 space separated values represent the following features
0. video number
1. user number
2. yaw distribution - 25th percentile
3. yaw distribution - mean
4. yaw distribution - 75th percentile
5. pitch distribution - 25th percentile
6. pitch distribution - mean
7. pitch distribution - 75th percentile
8. %of the sphere covered during the time window
9. Maximum angle moved from initial position - pitch
10. Maximum angle moved from initial position - yaw
11. head movement speed in yaw - 25th percentile
12. head movement speed in yaw - mean
13. head movement speed in yaw - 75th percentile
14. head movement speed in pitch - 25th percentile
15. head movement speed in pitch - mean
16. head movement speed in pitch - 75th percentile


The folder Sample Videos contain several videos used in this dataset. To download all videos, please refer to the corresponding original datasets/papers.



## Additional features and visualizations


## References
<a id="1">[1]</a> 
Xavier Corbillon, Francesca De Simone, and Gwendal Simon. 2017. 360-Degree Video Head Movement Dataset. In Proceedings of the 8th ACM on Multimedia Systems Conference. ACM, Taipei Taiwan, 199–204. https://doi.org/10.1145/3083187.3083215 

<a id="2">[2]</a> 
Wen-ChihLo, Ching-LingFan, Jean Lee, Chun-Ying Huang, Kuan-Ta Chen,and Cheng-Hsin Hsu.2017. 360° Video Viewing Dataset in Head-Mounted Virtual Reality.In Proceedings of the 8th ACM on Multimedia Systems Conference.ACM, Taipei Taiwan, 211–216. https://doi.org/10.1145/3083187.3083219 

<a id="3">[3]</a> 
Yanan Bao, Huasen Wu, Tianxiao Zhang, Albara Ah Ramli, and Xin Liu.2016. Shooting a moving target: Motion-prediction-based transmission for 360-degree videos. In 2016 IEEE International Conference on Big Data (Big Data). IEEE,Washington DC, USA ,1161–1170. https://doi.org/10.1109/BigData.2016.7840720 

<a id="4">[4]</a> 
Chenglei Wu, Zhihao Tan, Zhi Wang, and Shiqiang Yang. 2017. A Dataset for Exploring User Behaviors in VR Spherical Video Streaming. In Proceedings of the 8th ACM on Multimedia Systems Conference. ACM, Taipei Taiwan, 193–198. https://doi.org/10.1145/3083187.3083210 

<a id="5">[5]</a> 
Yu Guan, Chengyuan Zheng, Xinggong Zhang, Zongming Guo, and Junchen Jiang.2019. Pano: optimizing 360° video streaming with a better understanding of quality perception. In Proceedings of the ACM Special Interest Group on Data Communication. ACM, Beijing China,394–407. https://doi.org/10.1145/3341302.3342063 

<a id="6">[6]</a> 
Afshin Taghavi Nasrabadi, Aliehsan Samiei, Anahita Mahzari, Ryan P. McMahan, Ravi Prakash, Mylène C. Q. Farias, and Marcelo M. Carvalho. 2019. A taxonomy
and dataset for 360° videos. In Proceedings of the 10th ACM Multimedia Systems Conference. ACM, Amherst Massachusetts, 273–278. https://doi.org/10.1145/3304109.3325812 
