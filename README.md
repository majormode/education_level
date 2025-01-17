# Education Levels

Python library listing educational stages per country.

Educational stages are subdivisions of formal learning, typically covering early childhood education, primary education, secondary education and tertiary education.

Education during childhood and early adulthood is typically provided through either a two- or three-stage system of childhood school, followed by additional stages of higher education or vocational education for those who continue their formal education:

- Early childhood education at preschool, nursery school, or kindergarten (outside the U.S. and Canada)
- Primary education at primary school or elementary school, and sometimes in the early years of middle school
- Secondary education at secondary school or high school, and sometimes in the latter years of middle school
- Higher education or vocational education

The following table introduces the main concepts, although terms and ages may vary in different places:

    +=====+===========================+================+================+=======+
    | Age |     Educational stage     | 2-stage system | 3-stage system | ISCED |
    +=====+===========================+================+================+=======+
    |  4  |                           | 	           |                |       |
    +-----+ Early childhood education |   Preschool    |   Preschool    |   0   |
    |  5  |                           |                |                |       |
    +-----+---------------------------+----------------+----------------+-------+
    |  6  |	                          |                |                |       |
    +-----+                           |                |                |       |
    |  7  |                           |                |                |   1   |
    +-----+                           |                |                |       |
    |  8  |                           |                |   Elementary   |       |
    +-----+                           |                |     school     +-------+
    |  9  |     Primary education     | Primary school |                |       |
    +-----+                           |                |                |       |
    | 10  |                           |                |                |       |
    +-----+                           |                +----------------|       |
    | 11  |                           |                |                |       |
    +-----+                           |                |                |       |
    | 12  |                           |                |                |       |
    +-----+---------------------------+----------------+                |   2   |
    | 13  |                           |                |                |       |
    +-----+                           |                | Middle school  |       |
    | 14  |                           |                |                |       |
    +-----+                           |                |                |       |
    | 15  |                           |                |                |       |
    +-----+                           |                |                |       |
    | 16  |   Secondary education     |   Secondary    |                |       |
    +-----+                           |    School      +----------------+-------+
    | 17  |                           |                |                |       |
    +-----+                           |                |                |       |
    | 18  |                           |                |  High school   |   3   |
    +-----+                           |                |                |       |
    | 19  |                           |                |                |       |
    +-----+---------------------------+----------------+----------------+-------+

The International Standard Classification of Education (ISCED) is a statistical framework for organizing information on education maintained by the United Nations Educational, Scientific and Cultural Organization (UNESCO).

Examples:

```python
>>> from majormode.education import EducationLevel
>>> education_levels = EducationLevel.get_country_education_levels("FR")
>>> for education_level in education_levels:
>>> for education_level in education_levels:
...     print(education_level.grade_name)
...
Toute petite section
Petite section
Moyenne section
Grande section
Cours préparatoire
Cours élémentaire, 1ère année
Cours élémentaire, 2ème année
Cours moyen, 1ère année
Cours moyen, 2ème année
Sixième
Cinquième
Quatrième
Troisième
Seconde
Première
Terminale

>>> education_level = EducationLevel.find_by_grade_level('FR', 8)
>>> print(education_level.grade_name)
Cours moyen, 1ère année

>>> education_level = EducationLevel.find_by_grade_name('FR', 'Terminale')
>>> print(education_level.grade_level)
16

>>> education_level = EducationLevel.find_by_grade_short_name('FR', 'CE1')
>>> print(education_level.grade_level)
6
```
