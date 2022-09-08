# `%svy_logistic_regression`: A generic SAS macro for simple and multiple logistic regression and creating quality publication-ready tables using survey or non-survey data.

This repository was created for use by CDC programs to collaborate on public health surveillance related projects in support of the CDC Surveillance Strategy.  Github is not hosted by the CDC, but is used by CDC and its partners to share information and collaborate on software.

## Macro description
Reproducible research is increasingly gaining interest in the research community. Automating the production of research manuscript tables from statistical software can help increase the reproducibility of findings. Logistic regression is used in studying disease prevalence and associated factors in epidemiological studies and can be easily performed using widely available software including SAS®, SUDAAN, Stata or R. However, output from these software must be processed further to make it readily presentable. There exist several procedures developed to organize regression output, though many of them suffer limitations of flexibility, complexity, lack of validation checks for input parameters, as well as inability to incorporate survey design

We developed a SAS® macro, %svy_logistic_regression, for fitting simple and multiple logistic regression models. The macro also creates quality publication-ready tables using survey or non-survey data which aims to increase transparency of data analyses. It further significantly reduces turn-around time for conducting analysis and preparing output tables while also addressing the limitations of existing procedures. In addition, the macro allows for user-specific actions to handle missing data as well as use of replication-based variance estimation methods.

The SAS® code presented in this macro is comprehensive, easy to follow, manipulate and to extend to other areas of interest. It can also be incorporated quickly by the statistician for immediate use. It is an especially valuable tool for generating quality, easy to review tables which can be incorporated directly in a publication. The macro has being developed to run on windows platform and might require appropriate adjustments to run on other operating systems platforms.

## How to use the Macro
The user should specify input parameters described in the table below unless the description is prefixed by (optional). The user, however, does not interact with the sub-macros. To achieve full potential of the SAS macro, the user must ensure that the analysis dataset is clean, analysis variables are well labelled, and values of variables have been converted into appropriate SAS formats before they can be input to the macro call.

|Parameter|Description|
|---------|-----------|
| `%svy_unilogit` and `%svy_multilogit` macros |
|dataset		|name of input dataset|
|truthvar	|name of reference/truth variable e.g., abbott_plasma_vl|
|truthcutvalue	|cutoff value to use to categorize values of test variable as having disease or not e.g., 1,000 so that if value ≥ 1,000 then presence of disease, otherwise absence of disease|
|testvarlist	|list of diagnostic test variable(s) separated by space e.g., vdbs_vl mdbs_vl ddbs_vl|
|testcutvalue	|cutoff value to use to categorize values of test variable as having disease or not e.g., 1,000 so that if value ≥ 1,000 then presence of disease, otherwise absence of disease|
|domain		|(optional) domain variable for sub-population analysis|
|domainvalue	|(optional) value of domain/sub-population of interest (should be numeric). Required if domain is specified|
|condition	|(optional) any conditional statements to create and or fine-tune the final analysis dataset specified using one IF statement|
|outputdir	|path for directory/folder where output is saved|
|tablename	|short name of output table|
|tabletitle	|title of output table|
|surveyname	|abbreviation for survey/study to be included in the output|
|decimalpoints	|number of decimal places for each estimated measure|
|alpha		|(optional) desired level of significance (default=0.05, for 95% confidence intervals)|
|missvaluelabel	|(optional) value label for missing values. If missing data have a format, it should be provided, otherwise macro assumes the default format “.”|
|varmethod  |(optional) method for computing confidence intervals namely "Normal" (default) for normal distribution or "Wilson" (most desired) for Wilson score or "Exact" for exact binomial approximations|
|print	|variable for displaying/suppressing the output table on the output window which takes the values (NO=suppress output, YES=show output)|

A sample macro call program, "svy logistic regression anafile.sas", is also provided as part of this repository.

A manuscript describing more details about the macro contents and usage is available online at: https://doi.org/10.1371/journal.pone.0214262

## Public Domain
This repository constitutes a work of the United States Government and is not
subject to domestic copyright protection under 17 USC § 105. This repository is in
the public domain within the United States, and copyright and related rights in
the work worldwide are waived through the [CC0 1.0 Universal public domain dedication](https://creativecommons.org/publicdomain/zero/1.0/).
All contributions to this repository will be released under the CC0 dedication. By
submitting a pull request you are agreeing to comply with this waiver of
copyright interest.

## License
The repository utilizes code licensed under the terms of the Apache Software
License and therefore is licensed under ASL v2 or later.

This source code in this repository is free: you can redistribute it and/or modify it under
the terms of the Apache Software License version 2, or (at your option) any
later version.

This source code in this repository is distributed in the hope that it will be useful, but WITHOUT ANY
WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A
PARTICULAR PURPOSE. See the Apache Software License for more details.

You should have received a copy of the Apache Software License along with this
program. If not, see http://www.apache.org/licenses/LICENSE-2.0.html

The source code forked from other open source projects will inherit its license.


## Privacy
This repository contains only non-sensitive, publicly available data and
information. All material and community participation is covered by the
Surveillance Platform [Disclaimer](https://github.com/CDCgov/template/blob/master/DISCLAIMER.md)
and [Code of Conduct](https://github.com/CDCgov/template/blob/master/code-of-conduct.md).
For more information about CDC's privacy policy, please visit [http://www.cdc.gov/privacy.html](http://www.cdc.gov/privacy.html).

## Contributing
Anyone is encouraged to contribute to the repository by [forking](https://help.github.com/articles/fork-a-repo)
and submitting a pull request. (If you are new to GitHub, you might start with a
[basic tutorial](https://help.github.com/articles/set-up-git).) By contributing
to this project, you grant a world-wide, royalty-free, perpetual, irrevocable,
non-exclusive, transferable license to all users under the terms of the
[Apache Software License v2](http://www.apache.org/licenses/LICENSE-2.0.html) or
later.

All comments, messages, pull requests, and other submissions received through
CDC including this GitHub page are subject to the [Presidential Records Act](http://www.archives.gov/about/laws/presidential-records.html)
and may be archived. Learn more at [http://www.cdc.gov/other/privacy.html](http://www.cdc.gov/other/privacy.html).

## Records
This repository is not a source of government records, but is a copy to increase
collaboration and collaborative potential. All government records will be
published through the [CDC web site](http://www.cdc.gov).

## Notices
Please refer to [CDC's Template Repository](https://github.com/CDCgov/template)
for more information about [contributing to this repository](https://github.com/CDCgov/template/blob/master/CONTRIBUTING.md),
[public domain notices and disclaimers](https://github.com/CDCgov/template/blob/master/DISCLAIMER.md),
and [code of conduct](https://github.com/CDCgov/template/blob/master/code-of-conduct.md).

## ----- for use in template only -----
## Hat-tips
Thanks to [18F](https://18f.gsa.gov/)'s [open source policy](https://github.com/18F/open-source-policy)
and [code of conduct](https://github.com/CDCgov/code-of-conduct/blob/master/code-of-conduct.md)
that were very useful in setting up this GitHub organization. Thanks to CDC's
[Informatics Innovation Unit](https://www.phiresearchlab.org/index.php/code-of-conduct/)
that was helpful in modeling the code of conduct.

## ----- for use in template only -----

