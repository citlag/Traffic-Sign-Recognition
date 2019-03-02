Copyright 2019 UTBM

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.


1. About this file
This ReadMe.txt is attached to the extended German Traffic Sign Detection Benchmark (GTSDB) dataset. The dataset contains mask labels added to the 
work of Meletis and Dubbleman. You are free to use this data only for research purposes. If you use it in a scientific publication, we want to 
ask you to cite the following papers:

@article{serna2018classification,
  title={Classification of Traffic Signs: The European Dataset},
  author={Serna, Citlalli G{\'a}mez and Ruichek, Yassine},
  journal={IEEE Access},
  volume={6},
  pages={78136--78148},
  year={2018},
  publisher={IEEE}
}

@inproceedings{heterogeneous2018,
  title={Training of Convolutional Networks on Multiple Heterogeneous Datasets for Street Scene Semantic Segmentation},
  author={Panagiotis Meletis and Gijs Dubbelman},
  booktitle={2018 IEEE Intelligent Vehicles Symposium (IV)},
  year={2018}
}

@inproceedings{Houben-IJCNN-2013,
   author = {Sebastian Houben and Johannes Stallkamp and Jan Salmen and Marc Schlipsing and Christian Igel},
   booktitle = {International Joint Conference on Neural Networks},
   title = {Detection of Traffic Signs in Real-World Images: The {G}erman {T}raffic {S}ign {D}etection {B}enchmark},
   number = {1288},
   year = {2013},
}


2. Content of the dataset
Along with this file you should have received:
a) train and test folders with three ground truth formats 
a) the semantics folder in each set(600 images for train and 300 images for test), contains the traffic sign masks following the Mapillary format 
with 2 classes (traffic signs front and background).
b) the instances folder in each set, contain 16 bit images where the first 8 correspond to the semantic class and the last 8 to the instance ID. 
c) a txt file named "GT_train" and "GT_test" in each corresponding folder, where the image number, RoI and traffic sign label are saved.


3. Explanation of ground truth formats

Semantics labels
Each image pixel is labelled with 2 classes following the Mapillary format:
ID = Label name -> RGB color
50 = traffic sign (front) -> (220,200,0)
65 = unlabeled -> (0,0,0)

Instance labels
Each image pixel is labelled with a unique ID for each traffic sign instance. The 16 bits images store in the first 8 bits the semantic id 
while in the last 8 bits the instance IDs are stored. 
The instance IDs start from 1 to n, depending on the number of traffic signs in each image.

Detection labels
The GT_train.txt and GT_test.txt files, contain the RoIs information of each traffic sign together with its corresponding label class and image number.
The information is stored in the following way:
ImageNumber.ppm;X1;Y1;X2;Y2;ClassID
The first field refers to the image file where the traffic sign is located in. Field 2 to 5 describe the region of interest (ROI) in that image. 
Finally, the ClassID is an integer number representing the traffic sign class. 

The traffic sign classes and their corresponding categories are defined as follows:
## Categories ##
Danger (0-33)
Priority (34-39)
Prohibitory (40-78)
Mandatory (79-97)
Special regulations (98-125)
Information (126-137)
Direction (138-145)
Additional panels (146-158)
Others (159-163)

## Classes ##
0	=	Right bend
1	=	Left bend
2	=	Double bend (left)
3	=	Double bend (right)
4	=	Dangerous descent
5	=	Steep ascent
6	=	Carriageway narrows (both)
7	=	Carriageway narrows (right)
8	=	Carriageway narrows (left)
9	=	Road leads on to quay or river bank
10	=	Uneven road (1 bump)
11	=	Uneven road (2 bump)
12	=	Slippery road
13	=	Loose gravel
14	=	Falling rocks
15	=	Pedestrian crossing
16	=	Children (School)
17	=	Cyclists entering or crossing
18	=	Domestic animals crossing
19	=	Wild animals crossing
20	=	Road works
21	=	Light signals
22	=	Intersection
23	=	Intersection with road
24	=	Roundabout
25	=	Two-way traffic
26	=	Level-crossings with gates
27	=	Other level-crossings
28	=	Inmediate level-crossing
29	=	Level-crossings additional signs
30	=	Airfield
31	=	Other dangers
32	=	Snow
33	=	Riders on horseback
34	=	Give way
35	=	Stop
36	=	Priority road
37	=	End of priority
38	=	Priority for oncoming traffic
39	=	Priority over oncoming traffic
40	=	No entry
41	=	Closed to all vehicles in both directions
42	=	No entry for cycles
43	=	No entry for vehicle drawing a trailer
44	=	No entry for power driven vehicles
45	=	No entry for vehicles having an overall widh exceeding … meters 
46	=	No entry for vehicles having an overall height exceeding … meters
47	=	No entry for vehicles exceeding … tonnes laden mass
48	=	No entry for vehicles having a mass exceeding … tonnes on one axle
49	=	No entry for trucks 
50	=	No left turn
51	=	No right turn 
52	=	No U-turn
53	=	Overtaking prohibited
54	=	Overtaking by goods vehicles prohibited
55	=	Maximum speed limit 10
56	=	Maximum speed limit 20
57	=	Maximum speed limit 25
58	=	Maximum speed limit 30
59	=	Maximum speed limit 40
60	=	Maximum speed limit 50
61	=	Maximum speed limit 60
62	=	Maximum speed limit 70
63	=	Maximum speed limit 80
64	=	Maximum speed limit 90
65	=	Maximum speed limit 100
66	=	Maximum speed limit 110
67	=	Maximum speed limit 120
68	=	Passing without stopping prohibited
69	=	End of all local prohibitions imposed on moving vehicles
70	=	End of maximum speed limit
71	=	End of prohibition of overtaking
72	=	End of prohibition of overtaking for goods vehicles
73	=	Parking prohibited 
74	=	Parking prohibited (first half month)
75	=	Parking prohibited (last half month)
76	=	Standing and parking prohibited 
77	=	End of parking prohibited 
78	=	No photos
79	=	Direction – Straight
80	=	Direction – Right
81	=	Direction – Left
82	=	Direction – Straight or Right
83	=	Direction – Straight or Left
84	=	Direction – Turn right
85	=	Direction – Turn left
86	=	Pass Right
87	=	Pass Left
88	=	Pass Either side
89	=	Compulsory roundabout
90	=	Compulsory cycle track
91	=	Compulsory footpath
92	=	Compulsory cycle track - footpath
93	=	Compulsory cycle track - footpath
94	=	Compulsory bus
95	=	End of compulsory bus
96	=	End of compulsory cycle track
97	=	End of pedestrian track
98	=	Lanes reserved for certain vehicle type
99	=	One-way (Straight)
100	=	One-way (Right)
101	=	One-way (Left)
102	=	Motorway
103	=	Road for motor vehicles
104	=	Beginning of area
105	=	End of area
106	=	Maximum speed zone
107	=	End of maximum speed zone
108	=	Pedestrian crossing
109	=	Parking
110	=	Parking for handicap
111	=	Parking for cars
112	=	Parking for goods vehicles
113	=	Parking for bus
114	=	Parking on pavement or verge
115	=	Parking on the right
116	=	Parking on the left
117	=	Parking garage
118	=	Bus stop
119	=	Cyclists-Pedestrians
120	=	Cycle track
121	=	Cyclists entering or crossing
122	=	Residential area
123	=	End of residential area
124	=	Uneven road (1 bump)
125	=	Pass right
126	=	End of road works
127	=	Filling station
128	=	Hotel or motel
129	=	Restaurant
130	=	Refreshments or cafeteria
131	=	Children on the road
132	=	School patrol
133	=	Water protection area
134	=	River
135	=	Road construction
136	=	Police station
137	=	Radio station
138	=	Advance direction signs
139	=	Direction to place
140	=	Number and direction of traffic lanes
141	=	Closure of a traffic lane
142	=	No through road
143	=	General speed limits
144	=	Exit from motorway
145	=	Carriage of vehicles
146	=	Distance to place
147	=	Length of dangerous section
148	=	Intersection priority
149	=	Ice/Snow
150	=	Directional panel (arrows)
151	=	Tram
152	=	Car
153	=	Bus
154	=	Truck
155	=	Handicap
156	=	Bicycle
157	=	Timing
158	=	Supplemental panel
159	=	Limited access on side
160	=	Curve right
161	=	Curve left
162	=	Barrier
163	=	Obstacle
665	=	Unknown

