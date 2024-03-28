<a name="readme-top"></a>

<!-- PROJECT SHIELDS -->
<!--
-->
[![Contributors][contributors-shield]][contributors-url]
[![LinkedIn][linkedin-shield]][linkedin-url]



<!-- PROJECT INFO -->
<br />
<div align="center">
<h3 align="center">HemOnc.org Cancer Ontology Made Easy</h3>

  <p align="center">
    A repo containing code that makes using Hemonc ontology easy
    <br />
  </p>
</div>



<!-- TABLE OF CONTENTS -->
<details>
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#about-the-project">About The Project</a>
    </li>
  </ol>
</details>


<!-- ABOUT THE PROJECT -->
## About The Project

[HemOnc.org](https://hemonc.org/wiki/Main_Page) is the largest freely available medical wiki of interventions, regimens, and general information relevant to the fields of hematology and oncology. It is designed for easy use and intended for healthcare professionals.

For data professional, the hemonc team has released their [ontology](https://hemonc.org/wiki/Ontology) which is freely available for academic and non-commercial use via [HemOnc Dataverse](https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/FPO4HB).

The ontology is structured based upon the OMOP data model and thus revolves around two main tables. One table contains concepts, this can be things such as drugs, diseases, treatment types, etc. The other contains a series of relationships between concepts. Taking as an example a non-cancer drug that we are all familiar with, 'Ibuprofen' and 'Anti-inflammatory' could be two concepts within the concept table. We could then have a relationship of 'Is a' between 'Ibuprofen' and 'Anti-inflammatory' so that:

'Ibuprofen' -> 'Is a' -> 'Anti-inflammatory'

Given that cancer regimens and treatments are constantly evolving and can be related in complex way, it is apparent the usefullness of such data.

For this reason, I am publishing a repo containing code that make it easy to interpret and utilize the data. 

You will find code snippets organized in folders depending on their function. Here is the list:

- Use recursion to easily tie drugs to their regimen types
    - In the ontology provided by Hemonc, often there is no direct relationship that can tell us whether a certain drug is chemotherapeutic or immunotherapeutic. 
    - Indeed, these relationships are often of the 2nd degree, i.e. a drug is related to a concept that is related to being chemotherapeutic. 
    - For this reason, the code hosted in [recursion](recursion.Rmd) showcases how to recurse over the [concepts](data/concept.csv) and [concept relationships](data/concept_relationship.csv) tables(which are stored in the data folder) to make this easily possible. You can view the rendered Rmarkdown in [recursion.html](recursion.html). 
    - The code starts with all drugs concepts and performs recursion to output all relationships of any degrees of type 'Is a' between drugs and higher level concepts.
    - It is also possible to ingest the hemonc tables into a SQL database, in which case I will be posting recursive CTE code to achieve the same output.
    - I am also going to upload python code to achieve the end result.

<!-- CONTACT -->
## Contact

Giorgio Di Salvo - disalvogiorgio97@gmail.com

<p align="right">(<a href="#readme-top">back to top</a>)</p>





<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
[contributors-shield]: https://img.shields.io/github/contributors/PerifanosPrometheus/HemOncOntologyMadeEasy.svg?style=for-the-badge
[contributors-url]: https://github.com/PerifanosPrometheus
[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=for-the-badge&logo=linkedin&colorB=555
[linkedin-url]: https://www.linkedin.com/in/giorgiodisalvo/