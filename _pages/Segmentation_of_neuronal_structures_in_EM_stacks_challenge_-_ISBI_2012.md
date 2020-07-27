[[Image:ISBI-logo.jpg|100px|right]]The [http://www.biomedicalimaging.org/ IEEE International Symposium on Biomedical Imaging (ISBI)] is the premier forum for the presentation of technological advances in theoretical and applied biomedical imaging and image computing. In the context of the [http://www.biomedicalimaging.org/2012/ ISBI 2012] conference which was held in Barcelona, Spain, from 2 to 5 May 2012, we organized a [http://www.biomedicalimaging.org/2012/index.php/programme/isbi-challenges/13-challenges/49-contest-workshop-segmentation-of-neuronal challenge workshop] on '''segmentation of neuronal structures in EM stacks'''. 


[[Image:Challenge-ISBI-2012-sample-image.png|thumb|500px|Example of ssTEM image and its corresponding segmentation]]In this '''challenge''', a full stack of EM slices will be used to train [[wikipedia:Machine learning|machine learning]] algorithms for the purpose of '''automatic segmentation of neural structures'''. 


The images are representative of actual images in the real-world, containing some noise and small image alignment errors. None of these problems led to any difficulties in the manual labeling of each element in the image stack by an [http://albert.rierol.net expert human neuroanatomist]. The aim of the challenge is to compare and rank the different competing methods based on their pixel and object classification accuracy.



==Relevant dates==
* '''Deadline for submitting results''': <del>February 1<sup>st</sup></del> March 1<sup>st</sup>, 2012

* '''Notification of the evaluation''': <del>February 21<sup>st</sup></del> March 2<sup>nd</sup>, 2012

* '''Deadline for submitting abstracts''': <del>March 1<sup>st</sup></del> March 9<sup>th</sup>, 2012

* '''Notification of acceptance/presentation type''': <del>March 15<sup>th</sup></del> March 16<sup>th</sup>, 2012

The workshop competition is done but '''the challenge remains open for new contributions'''.

==How to participate==
'''Everybody''' can participate in the challenge. The only requirement consists of filling up the registration form [http://brainiac2.mit.edu/isbi_challenge/user/register here] to get a user name and password to download the data and upload the results.

This challenge was part of a [http://www.biomedicalimaging.org/2012/index.php/programme/opensourceworkshops workshop] previous to the [http://www.biomedicalimaging.org/2012/ IEEE International Symposium on Biomedical Imaging (ISBI) 2012]. After the publication of the evaluation ranking, teams were invited to submit an abstract. During the workshop, participants had the opportunity to present their methods and the results were discussed.  

Each team received statistics regarding their results. '''After the workshop, an overview article will be compiled by the organizers of the challenge, with up to three members per participating team as co-authors'''.

If you have any doubt regarding the challenge, please, do not hesitate to contact the [[Segmentation_of_neuronal_structures_in_EM_stacks_challenge_-_ISBI_2012#Organizers|organizers]]. There is also an '''open discussion group''' that you can join [http://groups.google.com/group/EM-segmentation-challenge-ISBI-2012 here].

==Training data==
[[Image:Challenge-ISBI-2012-Animation-Input-Labels.gif|thumb|400px|Input training data and corresponding labels]]
The training data is a set of 30 sections from a serial section Transmission Electron Microscopy (ssTEM) data set of the Drosophila first instar larva ventral nerve cord (VNC). The microcube measures 2 x 2 x 1.5 microns approx., with a resolution of 4x4x50 nm/pixel.

The corresponding binary labels are provided in an in-out fashion, i.e. white for the pixels of segmented objects and black for the rest of pixels (which correspond mostly to membranes).

'''To get the training data, please, register in the [http://brainiac2.mit.edu/isbi_challenge/ challenge server], log in and go to the "Downloads" section'''.

This is the only data that participants are allowed to use to train their algorithms.

==Test data==
The contesting segmentation methods will be ranked by their performance on a test dataset, also available in the [http://brainiac2.mit.edu/isbi_challenge/ challenge server], after registration. This test data is another volume from the same Drosophila first instar larva VNC as the training dataset.

==Results format==
The '''results''' are expected to be uploaded in the [http://brainiac2.mit.edu/isbi_challenge/ challenge server] as a '''32-bit TIFF 3D image, which values between 0 (100% membrane certainty) and 1 (100% non-membrane certainty).'''

==Evaluation metrics==
In order to evaluate and rank the performances of the participant methods, we will use 2D topology-based segmentation metrics, together with the pixel error (for the sake of metric comparison). Each metric will have an updated leader-board. 

The metrics are:

* [[Minimum Splits and Mergers Warping error]], a segmentation metric that penalizes topological disagreements, in this case, the object splits and mergers.
* '''Foreground-restricted Rand error''': defined as 1 - the maximal [[wikipedia:F1 score|F-score]] of the foreground-restricted [[wikipedia:Rand index|Rand index]], a measure of similarity between two clusters or segmentations. On this version of the Rand index we exclude the zero component of the original labels (background pixels of the ground truth).
* '''Pixel error''': defined as 1 - the maximal [[wikipedia:F1 score|F-score]] of pixel similarity, or squared Euclidean distance between the original and the result labels.

If you want to apply these metrics yourself to your own results, you can do it within Fiji using this [[Segmentation evaluation metrics - Script|script]].

We understand that segmentation evaluation is an ongoing and sensitive research topic, therefore we open the metrics to discussion. Please, do not hesitate to contact the [[Segmentation_of_neuronal_structures_in_EM_stacks_challenge_-_ISBI_2012#Organizers|organizers]] to discuss about the metric selection.

==Organizers==
* {{Person|Iarganda}} (Howard Hughes Medical Institute, Department of Brain and Cognitive Sciences, Massachusetts Institute of Technology, Cambridge, MA, USA)
* [http://hebb.mit.edu/people/seung/ Sebastian Seung] (Howard Hughes Medical Institute, Department of Brain and Cognitive Sciences, Massachusetts Institute of Technology, Cambridge, MA, USA)
* {{Person:Albertcardona}} (Institute of Neuroinformatics, Uni/ETH Zurich, Switzerland)
* {{Person|Schindelin}} (University of Wisconsin-Madison, WI, USA)

==References==
Publications about the data:

* {{Cite journal
  | author = Albert Cardona, Stephan Saalfeld, Stephan Preibisch, Benjamin Schmid, Anchi Cheng, Jim Pulokas, Pavel Tomancak and Volker Hartenstein
  | title = An Integrated Micro- and Macroarchitectural Analysis of the ''Drosophila'' Brain by Computer-Assisted Serial Section Electron Microscopy
  | journal = PLoS Biol
  | year = 2010
  | volume = 8
  | pages = e1000502
  | number = 10
  | month = 10,
  | doi = 10.1371/journal.pbio.1000502
  | publisher = Public Library of Science
  | url = http://dx.doi.org/10.1371%2Fjournal.pbio.1000502
}}

Publications about the metrics:
* {{cite journal
  |author = V. Jain, B. Bollmann, M. Richardson, D.R. Berger, M.N. Helmstaedter, K.L. Briggman, W. Denk, J.B. Bowden, J.M. Mendenhall, W.C. Abraham, K.M. Harris, N. Kasthuri, K.J. Hayworth, R. Schalek, J.C. Tapia, J.W. Lichtman, S.H. Seung
  | title = Boundary Learning by Optimization with Topological Constraints
  | booktitle = 2010 IEEE CONFERENCE ON COMPUTER VISION AND PATTERN RECOGNITION
	(CVPR)
  |  year = 2010
  |  series = IEEE Conference on Computer Vision and Pattern Recognition
  |  pages = 2488-2495
  |  organization = IEEE Comp Soc
  |  doi = 10.1109/CVPR.2010.5539950
}}

[[Category:Segmentation]]