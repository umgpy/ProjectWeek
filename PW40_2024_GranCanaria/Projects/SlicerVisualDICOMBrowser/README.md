---
layout: pw40-project

permalink: /:path/

project_title: Visual DICOM browser
category: DICOM
presenter_location: In-person

key_investigators:
- name: Davide Punzo
  affiliation: Freelancer 
  country: France
  
- name: Andras Lasso
  affiliation: Perk Labs 
  country: Canada

- name: Steve Pieper
  affiliation: Isomics, Inc.
  country: USA

- name: Jean-Christophe Fillion-Robin
  affiliation: Kitware
  country: USA

- name: anyone is welcome!
  affiliation: 
  country:   
---

# Project Description
The visual DICOM browser provides a new user interface for quick viewing and retrieval of patient images stored on remote DICOM servers. The new tool is optimized for clinical workflows where the focus is on all the images of a single patient - as opposed to the existing DICOM browsing experience, which was more suitable for bringing together images from many patients.

Both server and local content at the same place and are visualized by thumbnails. All data is retrieved in the background using classic DIMSE networking (most commonly used protocols in hospitals), in multiple concurrently running threads. The currently supported operations are:

- Browsing and filtering with thumbnails of content of local DICOM database and multiple remote DICOM servers.
- Query/Retrieve data from servers (DIMSE `C-FIND`, `C-GET`, `C-MOVE` SCU). All the operations are done in background and in parallel. Downloaded data is automatically cached in the local DICOM database. A unique feature is the possibility to retrieve images using C-GET protocol (suitable for cases when many Slicer instances are running in docker containers) with a clinical PACS that only supports C-MOVE protocol (most clinical PACS), via a proxy server (such as the free Orthanc).
- Import data from local files.
- Receive data sent from remote PACS (DIMSE `C-STORE` SCP).
- Send data to remote PACS (DIMSE `C-STORE` SCU).
- Quick browsing of all DICOM metadata and pixel data.
- Remove data from local database (not from server).

The widget is currently an experimental feature in Slicer (DICOM module). Current Roadmap is at [link](https://github.com/commontk/CTK/issues/1162).

Possible longer-term ENH to discuss/work during the project week:
- add data streaming from visual brower series widgets to Slicer volume nodes.
- add jobs list UI (e.g. current status, actions to stop/force retry etc..., error report per job).
- handle jobs queue in the scheduler by file (so we can restart the jobs/workers at application restart).
- implementing send in C++ at ctk level (i.e. adding `ctkDICOMSendJob`, `ctkDICOMSendWorker` and `ctkDICOMSend` with underlining DIMSE `DcmStorageSCU`). This would allow to use the background/parallel operations infrastructure for SEND as well.
- add `DICOMweb`.

## Objective
Finalize the ctk visual DICOM browser:

1. Get feedback from users/developers. Reference: [Roadmap](https://github.com/commontk/CTK/issues/1162).
1. Discuss/start implementing the longterm ENH.

## Approach and Plan

1. Have a meeting/demo with people interested for colletting feedback.  
1. Prioritize/coordinated any future development based on the feedback.

## Progress and Next Steps

1. ...
1. ...


# Illustrations
screenshots:

<img src="https://github.com/NA-MIC/ProjectWeek/assets/7985338/86088d74-650b-4139-8e1f-66d0794b73f7" width="1000">
<img src="https://github.com/NA-MIC/ProjectWeek/assets/7985338/00c4bf23-961b-407b-8730-085d54244a53" width="1000">

video:

<video
   autoplay muted loop
   src="https://github.com/NA-MIC/ProjectWeek/assets/7985338/01c5bb63-87e6-4e37-84e1-ce11b57f6bb5"
   style="width:1000px">
</video>


UML Diagram:

<img src="https://github.com/NA-MIC/ProjectWeek/assets/7985338/f115d6cc-9ca2-4f06-ac79-0001c565952e" width="1000">


# Background and References

[PW38 Project](https://projectweek.na-mic.org/PW38_2023_GranCanaria/Projects/SlicerVisualDICOMbrowser/)

[CTK PR1](https://github.com/commontk/CTK/pull/1142)

[CTK PR2](https://github.com/commontk/CTK/pull/1165)

[Slicer PR](https://github.com/Slicer/Slicer/pull/7525)

[Roadmap](https://github.com/commontk/CTK/issues/1162)

[Logging UI CTK PR](https://github.com/commontk/CTK/pull/1184)
