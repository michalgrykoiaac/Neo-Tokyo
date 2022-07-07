# Neo-Tokyo
Neo Tokyo Generative Cities


The focus of our analysis and city generation is the polycentric nature of Tokyo and the juxtapositions of building cluster types and heights.  We have combined 3 methods in order to achieve this: first generating the starting graph network using a DC GAN to understand the dense network of Tokyo, then manually analysing Tokyo’s districts using OSMNX to understand the core network and finally clustering existing building types from the sampled zones to get an understanding of categories and groupings.  All this together would create NeoTokyo.

<img width="1478" alt="city samples" src="https://user-images.githubusercontent.com/97453175/177810899-c4d41fa5-0544-4922-b44a-867f8e276094.png">

First step involved the initial network graph generation using GAN algorithms to predict the density of Tokyo’s districts. We chose image generation for its speed and ease to create MANY 2D NETWORK samples.  Using a deep convolutional GAN, the AI  architecture works by estimating the  generative models using samples between real models and discriminating between the real and fake samples created.  We created 2000 images samples from districts across Tokyo, by tiling the city into 1000m grids from OSM data and creating png images from them.

<img width="1364" alt="detailedClustering" src="https://user-images.githubusercontent.com/97453175/177810928-eb98f8cd-ad6b-4700-9570-3d0e674952d1.png">
The final part of gathering building data and heights was generated through clustering existing OSM data across 4 large dense districts.

Each district had specific building categories which were counted by centroid and then clustered to created individual zones, then added to a database.  Elbow analysis was used to predict the best number of clusters and was repeated for all four samples districts.

The final city generation was accomplished through the combined cluster building zones and network so that we allocate a category to each section and overlay with the network.

![neoTokyo cover](https://user-images.githubusercontent.com/97453175/177810834-90c9835a-11bd-4387-97a0-d0fb14a184ec.jpg)

NeoTokyo is a project of IAAC, Institute for Advanced Architecture of Catalonia developed in the Master of Advanced Computation in Architecture and Design 2021/22 by STUDENTS: MICHAL GRYKO + TAKEAKI SAKAKIBARA SENIOR FACULTY: DAVID ANDRES LEON FACULTY ASSISTANT: DAI KANDIL

Blog: https://www.iaacblog.com/programs/neotokyo-geometric-optimization/
