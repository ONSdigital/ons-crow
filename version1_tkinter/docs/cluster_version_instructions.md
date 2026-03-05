# CROW Cluster Version Instructions

> [!NOTE]
> 
> All exemplar data displayed in this document is synthetic.
> 
## Input File Requirements
The requirements for the files that you wish to clerically review are as
follows;
- The files must be CSV files.
- They must be 'long' files. There must be one row per record, containing
  identifiable variables that are to be presented to clerical matchers for
  review. Clusters will contain multiple rows. See below for an example
- There must be a column that represents cluster ID. These IDs can be any random
  string, so long as they are unique to each cluster.
- There must be a record ID column. This must be unique for each record.
Example 'long' file data format to be input to CROW:

![0_long_input_data.png](images/0_long_input_data.png)

## Setting Up the Config File (for project leads)
In order to adapt the cluster version of CROW to your data, you will need to
edit the `Config_clusters.ini` file to meet the needs of your project.
Instructions for doing this are self-contained within the config file, however,
below are the key options.
### [column_headers_and_order]
This is where you can specify what text you want to appear as the header for
each row. This can be independent of the column headers in your CSV. You only
need to create titles for the variables you want to display.
### [column_file_info_and_order]
This is where you specify how CROW reads the variables in your CSV. Variable
titles in this field MUST be the same as in your CSV. You only need to create
titles for the variables you want to display.
### [cluster_id]
Specify which column is your cluster ID column (MUST be the same as in your
CSV).
### [record_id]
Specify which column is your record ID column (MUST be the same as in your CSV).
### [custom_settings]
There are a few optional custom settings that can be personalised for matching
projects. These include:

#### commentbox
When set to 1, a comment box is displayed as shown below that allows clerical
matchers to enter comments that will be appended to the relevant clusters in the
matched file. If set to 0, this is not displayed.

![1_comment_box_typing.png](images/1_comment_box_typing.png)

#### comment_values
Shows example dropdown options for the comment box that can be selected by
clerical matchers. If left blank, no options are shown.

![2_comment_box_dropdown.png](images/2_comment_box_dropdown.png)

## Using the Cluster Version
To use the Cluster Version of CROW; users can simply click play in their given
Python editor. The below window will then pop-up.

![3_intro_window.png](images/3_intro_window.png)

Clerical matchers can then choose the file they wish to match. After selecting a
file the below window will pop-up.

![4_cluster_main_window.png](images/4_cluster_main_window.png

Users can then use the checkboxes on the left-hand side of the window to
highlight records they wish to match, followed by clicking the 'Match' button.
There can be multiple matches in a given cluster. Once all matches are
exhausted, or the 'No more matches' button is clicked, CROW will move on to the
next cluster for resolution.

If users wish to add a custom comment, or a pre-determined comment about records
in this cluster, a comment can be entered in the comment box (or selected from
the drop-down tool) before a matching decision is made.

The 'Back' button can be used to return to the previous decision. Pressed the
first time it will reset the current cluster (if some decisions have already
been made in that cluster). Pressed again it will take the user back to the
previous cluster.

## The Output

The output file will look something like this:

![An Excel sheet of CROW output.][cluster-output]

A match column is appended to each row. If the given record has a match, the
record for that record and all the matches will be stored in the 'Match' column
separated by a comma. If there are no matches to a given record 'No Matches In
Cluster' is added to the 'Match' column. To get your outputs in a pairwise
linked format (see image below) run the `CROW_cluster_output_updater.py` script.

![An Excel sheet of CROW output in pairwise (wide) format.][cluster-output-updater-output]

[cluster-main-window]: ./images/4_cluster_main_window.png
[cluster-output]: ./images/5_cluster_output.png
[cluster-output-updater-output]: ./images/6_cluster_output_updater_output.png
[comment-box-dropdown]: ./images/2_comment_box_dropdown.png
[comment-box-typing]: ./images/1_comment_box_typing.png
[intro-window]: ./images/3_intro_window.png
[long-input-data]: ./images/0_long_input_data.png

