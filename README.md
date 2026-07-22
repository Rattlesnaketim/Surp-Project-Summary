The content within this GitHub repository contains code that is still a work in progress. The code in this repository contains code I used to research the effects of baryonic matter on the tSZ within the FLAMINGO simulations.
These notebooks document my work from learning how to manuever with FLAMINGO data, to gathering data from the simulation.


**Helpful_Contextual_Documents**

-Cosmological feedback from a halo assembly perspective
  -https://arxiv.org/abs/2505.18258
  
-Shocks in the Stacked Sunyaev-Zel'dovich Profiles of Clusters II: Measurements from SPT-SZ + Planck Compton-y Map
  -https://arxiv.org/abs/2111.04778
  
-The Atacama Cosmology Telescope: A Catalog of > 4000 Sunyaev-Zel'dovich Galaxy Clusters
  -https://arxiv.org/abs/2009.11043
  
-The Atacama Cosmology Telescope: DR6 Sunyaev-Zel'dovich Selected Galaxy Clusters Catalog
  -https://arxiv.org/abs/2507.21459
  
-The universal galaxy cluster pressure profile from a representative sample of nearby systems (REXCESS) and the Y_SZ-M_500 relation
  -https://arxiv.org/abs/0910.1234

-The FLAMINGO project: Baryon effects on the matter power spectrum
  -https://arxiv.org/abs/2410.17109

-Deciphering Baryonic Feedback from ACT tSZ Galaxy Clusters
  -https://arxiv.org/abs/2507.04476

-Deciphering baryonic feedback with galaxy clusters
  -https://arxiv.org/abs/2402.00110
  -------------------------------------------------------------------------
  **FLAMINGO**
  
  -FLAMINGO is a suite of large-volume hydrodynamical simulations for cosmology and galaxy cluster physics. This currently the data that notebooks in this repository use. Our goal with using this is to hopefully gather data on baryonic feedback in the tSZ at different redshifts in different variations of feedback.
   The variations of feedback we use in this code is a 0 sigma variation which means relatively low feedback, does not mean no feedback, and a -8 sigma variation which means relatively high feedback. Our goal with this project is to get measurements of the tSZ in both of these scenarios and then use the data gathered from this data to compare with real cosmological data.
   This simulation uses integrated maps for its tSZ and kappa maps. We then also have halo lightcones that are used to determine the location of galaxy clusters/ Dark matter halos. The halos we are interested in this project so far is 76, 75, 72, 71, 67, and 64. Each of these catalogs are at different redshifts of 0.5, 0.1, 0.25, 0.3, 0.5, and 0.65.
   The Reason for these catalogs is due to us wanting to gather a general idea of the tSZ in each of these catalogs and see how the tSZ changes in each catalog in each variation.
  -------------------------------------------------------------------------
  **Explanation of Each File**
  
  cutout.ipynb
    
    -This notebook was created by Nihar Dalal and is code that was given to me to help me get familar with how we would be calculating the scatter of the tSZ as well as containing code that helped me get familiar with the healpix maps that I used for FLAMINGO.
     This code was mostly used as a reference/starter code for this SURP project and the rest is containing work that I created.
  Test.ipynb
    
    -This was the first notebook I created for this project. This code was mostly constructed for me to understand how to open files within FLAMINGO as well as gaining an understanding of what the code in cutout.ipynb works. 
  HealpixTesting.ipynb
    
    -This code was me familiarizing myself with healpix maps and some of the data within FLAMINGO. In this notebook I used this to discover what galaxy cluster would be the largest inside halo catalog 76. This code also generates plots for the tsz and its scatter but the scatter is too large.
     This also uses information from all galaxy clusters inside FLAMINGO instead of a select number of clusters that the other notebooks use. The reason this uses all clusters instead of the largest is due to me familiarizing myself with the data.
  FlamingoDataCone76.ipynb
    
    -This code used Healpix Testing as the skeleton for this code but instead I got rid of aspects we were not interested in such as the visualisation of each map since that is not important to what we are looking for. This code also acts as the skeleton for the other FlamingoDataCone files in this repository.
     This code also does not contain some functions that was in HealpixTesting due to them being unnecessary and to hopefully reduce run time. This codes purpose is to look at the 300 most massive clusters, seperated into 3 bins, in FLAMINGO at halo catalog 76, and then calculate the tsz, kappa, and the scatter of both for 0 sigma and 8 sigma variations.
     This code currently takes about 1 hour and 40 minutes to run and this is the same for the other FlamingoDataCones. The reason due to the high runtime of this code is mostly due to the final function in the code that is meant to run a for loop that calculates the tSZ, kappa, and scatter for each of the 3 bins.
  FlamingoDataCone75.ipynb
    
    -This code is a copy of the previous code and is currently a work in progress. This code currently has an extremely large scatter and currently I am writing code to hopefully reduce the scatter by using a bootstrap method rather than calculating by dividing the average by the amount of clusters to the 1/2 power.
     Currently the code will not compile due to me attempting to figure out how to use this bootstrap method on a 2d profile instead of the 1d profile requested. The reason for doing this is to not lose any valuable data if I were to transfer the current scatter to a 1d array.
  FlamingoDataCone72
    
    -This code was mostly to check if The Galaxy clusters are centered inside the healpix maps. This code shows that the clusters are currently not centered and requires more insight from the FLAMINGO dev team to hopefully have a solution for this.
  FlamingoDataCone71
    
    -This code is having the same exact issues that data cone 72 was having in relation to the galaxy clusters not being center in the healpix maps. This is causing both of these catalogs to produce data that is not accurate or properly represents the most massive clusters inside this catalog.
  -------------------------------------------------------------------------
  **Next Steps**
  
  -Our goals for our next steps is to reduce the scatter by usiung the bootstrap method which I am currently working on. We are also planning on contacting the devs of FLAMINGO in order to center the halo catalogs at further redshifts in order to gather data at further redshifts.
   After we gather the information from the other redshifts, we plan on comparing this data with data from ACT.
  -------------------------------------------------------------------------
  **Acknowledgments**
  
  Thank you to Nihar Dalal, Chris Hirata, and Chun-Hao for providing the guidance, resources, and support that made this project possible. I would also like to thank the FLAMINGO collaboration for developing and providing the simulation data that forms the foundation of this research.
  Finally, I would like to thank the Summer Undergraduate Research Program (SURP) for giving me the opportunity to participate in this research project. It has been an incredible experience that has strengthened my foundation as both an astronomer and a student, and I am grateful for the opportunity to contribute to this work!
  
