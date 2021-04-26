##Introduction
This Repository contains the population data created by the population synthesis tool by Johannes Ponge, Malte Enbergs and Michael Schlüngel.  
For now we created a population for every municipality in NRW.  
The populations are split in one csv per municipality named after the municipality id.  
A list of NRWs municipalitiy ids with their city names can be obtained from [recht.nrw.de](https://recht.nrw.de/lmi/owa/br_vbl_show_pdf?p_id=160).  

The populations themself always represent 100% of the municipalities population. Thereby each line represents one individual. 
Each individual has a variety of attributes, which refer to the household the individual lives in and the individual itself.  

##Short Attribute Overview
The attributes referring to the household are:
1. *household_id*: The id to identify a household and group its members
1. *municipality_id*: The id of the municipality the household beslongs to
1. *grid_id*: The id of the grid the household is located in
1. *HLA*: The Family Status of a household
1. *HSC*: The Senior Status of a household
1. *HSI*: The size of a household

The attributes referring to the individual are:
1. *age*: The conrete age of an individual
1. *SEX*: The sex of an individual
1. *AG2*: The age group a individual is in
1. *EMP*: The employment staus of an individual

##Detailed explanation of the attributes:

**household_id**  
The household id consists of the respective municipality id and a assigned number of teh household connected by a "-".

**municipality_id**
The municipality id of the household, the connection from municipality ids to city names can be obtained from [recht.nrw.de](https://recht.nrw.de/lmi/owa/br_vbl_show_pdf?p_id=160).

**grid_id**  
The grid_id refers to the census uses for geographical positioning. It represents the coordinate laying in the middle of a 100x100m square, in which the household should be placed. To get the coordinates from the grid id you take the Number after the N times 100 to have your northern position and do the same to the number after the E to have your eastern position. The coordinates are given in the *EPSG:3035* format.

**HLA**  
The family status of an household is defined by the core family of the household. The Family Status (HLA) generally informs the composition of households and the residents’ relationships. It is based on the definition of a core family, which consists of a defined index person and at least one further family member living in the household, who is either a child or the partner of the index person. The household can consist of either only the core family or also include additional members, who do not belong to the core family (Michel 2014). Therefore the characteristics of the Family Status are the different types of core families.  
The possible characteristics are:
1. *S*: A single person living in the household
1. *MC*:  A married couple living in the household
1. *PC*: A registered couple (same sex)
1. *PO*: A not formally registered couple
1. *SM*: A single mother living in the household
1. *SF*: A single father living in the household
1. *NA*: A household without a core family

**HSC**  
HSC defined the senior status of an household. A senior is defined as a person, who is 65 or older. It can have the following characteristics:
1. *OS*: Only seniors living in the household
1. *MIX*: Seniors and non seniors living in the household
1. *NA*: Only non-seniors living in the hosuehold

**HSI**  
HSI is the household size counting all members of an household. It is categorized in classes from one to six. Thereby every class represents the given size, exept the class 6, which can also represent households bigger than six.

**age**  
The age is a discrete number for each individual and represents the age in years. It was calculated during the synthetisation process by chance in the range of *AG2*.

**SEX**  
The SEX of an individual determines its gender. Possible characteristics are:
1.*F*: female
1.*M*: male

**AG2**  
AG2 represents the age group of the individual. The 2 refers to the way these age groups are distributed over the age ranges, as the census uses age groups in ten year steps (*AG1*), but we used a division into merketresearch relevant groups(*AG2*). The possible characteristics are:  
1. *0003*:  younger than 3
1. *0305*:  between 3 and 5
3. *0614*:  between 6 and 14
4. *1517*:  between 15 and 17
5. *1824*:  between 18 and 24
6. *2529*:  between 25 and 29
7. *3039*:  between 30 and 39
8. *4049*:  between 40 and 49
9. *5064*:  between 50 and 64
10. *6574*:  between 65 and 74
11. *75XX*: 75 or older

**EMP**  
EMP stands for the employment status of an individual. It uses the term employment person, which means that the person could be employed and non-employment person, which means that the person can not be employed (e.g. students, young children or seniors). It has the following characteristics:
1.*EMP*: employed
2.*UEP*: employmentperson, but unemployed
3.*NEP*: non-employment person
