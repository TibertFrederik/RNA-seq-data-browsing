# RNA-seq-data-browsing

#### This repository contains code used for creating the bulk RNA-seq data browsing app using Shiny. The app is connected to a directory named "data". Data contains shared bulk RNA-seq data stored as DESeq2 objects.
#### To update the data folder with new datasets, which are applicable to the app.R file follow the below instructions


To be accepted for upload to the data folder on Ucloud, the data **must** comply with the following requirements:

#### An example is given in dataset.prep.example.R 
  
- [x] The data must be in a DESeq2 object.

- [x] The DESeq2 object must include owner information: `mcols(DESeq2object)$owner <- "OWNER INITIALS"`

- [x] The DESeq2 object must have removed sizeFactor information: `DESeq2object$sizeFactor <- NULL` 

- [x] If model was adjusted during intial differential expression analysis, remove replaceable variable: `DESeq2object$replaceable <- NULL`

### Prerequisites for running the app on Ucloud: ###
- Have R with packages listed in the app.R script installed in a Drive names "Software" in the Group project.
- Make a folder such as /Software/Shiny_RNAseq and place the app.R script here. 
- Make a folder named data and place it in /Software.
- Place all DESeq2 objects with data to be shared in the /data folder 

### Running the app on Ucloud with predetermined or user-specified settings: ###
Open Ucloud and start a Shiny application [here](https://cloud.sdu.dk/app/jobs/create?app=shiny&version=4.2.0)
### Predetermined:
- Click "Import parameters" --> Click "Select file from Ucloud"
- Navigate to GROUP/Software/ and select ShinyParameters.json

#### Press submit

### User-specified settings:
Select an appropriate machine type:
- 23 GB RAM is a little better than your own computer 
- 94 GB ram is fast for this application

Select following folders:
- Input folder: GROUP -> Software -> RNAseqBrowsing
- Additional folder -> Software -> R

#### Press submit
#### Press open interface
- N.B.! Only press ONCE on "compute differential expression analysis". Genes can be looked up for the model used. Press only again if another model is to be used (e.g. with gender correction ~gender+treatment).

## Enjoy your data surf :) 
