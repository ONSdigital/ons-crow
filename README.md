# Clerical Resolution Online Widget (CROW)

The Clerical Resolution Online Widget (CROW) is an open-source project designed
to facilitate the clerical review of linked data.

Clerical matching is the process of manually reviewing records, as part of the data linkage process.

CROW is applicable for some but not all types of clerical matching work. CROW can be used: 1) To perform primary clerical matching in cases of uncertainty. It can be used to make a decision on a candidate pair of records or a cluster of records belonging to the same entity. 2) To assess the quality of automatic linkage. It can be used to verify candidate links and to check for false positives or false negatives. In both cases candidate pairs or clusters need to be identified by either automatic matching or by blocking, prior to the use of CROW.

CROW cannot be used for clerical search. It cannot be used to look for matches within a large pool of data

There are currently two types of CROW:

- **CROW1** - a desktop application made with Tkinter.
- **CROW2** - a web application made with Flask.

> [!IMPORTANT]
>
> CROW2 contains bugs that are currently under investigation. As such, we do not
> recommend its use. Please use CROW1 instead.

- [Getting Started](#getting-started)
  - [Documentation](#documentation)
- [Version Differences](#version-differences)
- [Contributing](#contributing)
- [Contact Us](#contact-us)
- [Acknowledgments](#acknowledgments)
- [License](#license)

## Getting Started

1. There are currently two main ways to access the CROW app:
   1. Clone the repo using Git (recommended, requires Git):

      ```sh
      git clone https://github.com/ONSdigital/ons-crow.git
      cd ons-crow
      ```

   2. Download the source code by opening the `Code` dropdown menu in the
      repository GitHub page and selecting `Download ZIP`.

2. Decide which version to run (see [Version Differences](#version-differences))
   and consult the corresponding documentation:

   - For desktop or external users, see [CROW1][crow1].
   - For internal ONS use, see [CROW1][crow1] (desktop) or [CROW2][crow2] (CDP).

### Documentation

The most up-to-date documentation can be found in the folders corresponding to
each version. There you will find instructions for setting CROW up for your
project as well as instructions you can give to your clerical reviewers on how
to run CROW once it is set up.

## Version Differences

The following should help you decide which version of CROW to use:

- CROW1 is a desktop application that reads files from your local file system,
  whereas CROW2 is integrated with the Cloudera Data Platform (CDP) and can
  access files stored in S3 buckets.
- CROW1 can only read CSV files, whereas CROW2 can only read parquet files.
- CROW1 consists of two separate scripts - `CROW_pairwise.py` and
  `CROW_clusters.py` - for if your data contains pairs or clusters of records.
  CROW2 is a single script (`flask_new_flow.py`) that treats all data as
  clustered. If you want to review pairwise data with CROW2 your data should be
  in long-file format (one record per row) and should still contain a cluster ID
  column (with only a pair of records in each cluster).
- CROW2 has various accessibility (based on [Web Content Accessibility
  Guidelines (WCAG) 2.0][accessibility-guidelines]) and feature improvements
  over CROW1, including:
  - Adjustable font formatting and style.
  - Muted colour brightness and highlighting.
  - Zoom and read-aloud functionality.
  - 'Select all' button for faster cluster review.

## Contributing

Contributions are welcome but please read [CONTRIBUTING.md][crow-contributing]
before submitting any changes.

## Contact Us

If you have additional questions or problems, please [check the
issues][crow-issues] or [open a new issue][crow-new-issue] according to the
[contributing guidelines][crow-contributing], or [contact us directly via
email][email].

## Acknowledgments

We are grateful to colleagues within the Data Linkage Hub and wider Office for
National Statistics for providing support, expert advice, and peer review of
this work.

## License

Unless stated otherwise, the codebase is released under the [MIT License][mit].
This covers both the codebase and any sample code in the documentation.

The documentation is [© Crown copyright][copyright] and available under the
terms of the [Open Government 3.0 license][ogl].

[accessibility-guidelines]: https://www.w3.org/TR/WCAG20/
[copyright]: http://www.nationalarchives.gov.uk/information-management/re-using-public-sector-information/uk-government-licensing-framework/crown-copyright/
[crow-contributing]: ./CONTRIBUTING.md
[crow1]: ./version1_tkinter/
[crow2]: ./version2_flask/
[crow-issues]: https://github.com/Data-Linkage/Clerical_Resolution_Online_Widget/issues
[crow-new-issue]: https://github.com/Data-Linkage/Clerical_Resolution_Online_Widget/issues/new
[email]: mailto:linkage.hub@ons.gov.uk
[mit]: ./LICENSE
[ogl]: http://www.nationalarchives.gov.uk/doc/open-government-licence/version/3/
