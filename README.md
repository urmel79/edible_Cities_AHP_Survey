# Introducing a procedure to perform the Analytic Hierarchy Process with own survey data obtained from *SoSci Survey* platform using R-package *ahpsurvey*

## Table of contents

<!--
@HINT:
auto-generate the TOC with the command line tool 'gh-md-toc' (https://github.com/ekalinin/github-markdown-toc) with following syntax:
$ cat README.md | ./tools/github-markdown-toc/gh-md-toc - > toc.md
-->

* [How to cite the project](#how-to-cite-the-project)
* [Aim of the project](#aim-of-the-project)
* [Short introduction](#short-introduction)
* [License](#license)

## How to cite the project

To make this **software project citable**, the Github repository has been linked to my [Zenodo](https://zenodo.org) account starting with **version 0.4 (pre-release)**. This and all subsequent updates to the project are now synchronized with Zenodo.

The **major advantage** of this linkage is that **version 0.4 (pre-release)** (and all subsequent releases) can be **scientifically cited** via their following **unique [DOI](https://en.wikipedia.org/wiki/Digital_object_identifier)**: 

[![DOI](https://zenodo.org/badge/565209300.svg)](https://zenodo.org/badge/latestdoi/565209300)

## Aim of the project

This paper will introduce, for the first time, a procedure in which data collected using the online survey platform [SoSci Survey](https://www.soscisurvey.de) are subsequently processed with the `ahpsurvey` package (see <cite data-cite="Vignettes_ahpsurvey_2019">Cho, 2019</cite>).

## Short introduction

The **Analytic Hierarchy Process (AHP)** is a common and now widely used method to decide on an alternative based on several different criteria (see <cite data-cite="Wikipedia_AHP">Wikipedia: AHP</cite>). Often the weighting of the respective criteria is done by a small number of decision makers or even a single decision maker. The AHP is then relatively easy to implement, both organizationally and technically.

Much less often, the weighting of criteria used for decision-making is done by a variety of different stakeholders. However, especially for decision-making with high social relevance, the involvement of many stakeholders is very important. At this point, the following questions arise:

1. How do I collect the data?
2. Which software or tool can perform an AHP with data from the survey of a large number of stakeholders?
3. How can data collection and processing be combined in a way that is both organizationally and technically sensible and time-effective?

As part of the DFG-funded project "Edible Cities", the objective was to evaluate different forms of urban agriculture using AHP with regard to their sustainability. The prerequisite for this was the involvement of numerous stakeholders from various target groups in the weighting of the previously selected criteria and sub-criteria. The pairwise comparisons of criteria and sub-criteria required for weighting should be performed by means of an online survey, which should ideally be followed directly by the AHP calculation automatically. Since the stakeholders interviewed here were predominantly people from the non-scientific environment, the survey had to be structured to suit these target groups.

To the authors' knowledge, the only online tool available for conducting a survey in combination with a directly subsequent criteria weighting is "AHP-OS" from [BPMSG (Business Performance Management Singapore)](https://bpmsg.com).

Reflecting the above requirements, especially with regard to the target groups, "AHP-OS" appeared unsuitable, however, as it is too strongly designed to generate consistent datasets. For this purpose, participants are asked to reconsider their decisions several times, if necessary, and to adjust them in the direction of consistency. This very scientific approach would not have been appropriate for the intended target groups.

Therefore, the authors followed the approach of separating the stakeholder survey and the subsequent weighting of the criteria in organizational and technical terms.

This paper introduces, for the first time, a procedure in which data collected using the online survey platform [SoSci Survey](https://www.soscisurvey.de) are subsequently processed with the `ahpsurvey` package (see <cite data-cite="Vignettes_ahpsurvey_2019">Cho, 2019</cite>). This package is exclusively available for the statistical programming language **R** and, to the authors' knowledge, is the only tool that meets the requirements outlined in the previous sections.

## License

This project is licensed under the terms of "GNU General Public License v3.0". For details see [LICENSE](./LICENSE).


