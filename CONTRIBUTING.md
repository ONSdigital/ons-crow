# Contributing

When contributing to this repository, please first discuss the change you wish
to make via issue, email, or any other method with the owners of this
repository before making a change.

- [Pull/merge request process](#pullmerge-request-process)
- [Code style](#code-style)
- [Review process](#review-process)
- [Retroactive commit signing](#retroactive-commit-signing)

## Pull/merge request process

1. Branch from the `main` branch. If you are implementing a feature name it
   `feature/name_of_feature`, if you are implementing a bugfix name it
   `bug/issue_name`.
2. Update the README.md and other documentation with details of major changes
   to CROW, this includes new configuration file parameters, useful features
   and user interface changes.
3. Once you are ready for review please open a pull/merge request to the
   `main` branch.
4. You may merge the Pull/Merge Request in once you have the sign-off of two
   maintainers.

## Code style

- We name variables using few nouns in lowercase, e.g. `mapping_names`
  or `increment`.
- We name functions using verbs in lowercase, e.g. `map_variables_to_names` or
  `change_values`.
- We use the [numpydoc][numpy-docs]
  format for documenting features using docstrings.

## Review process

1. When we want to release the package we will request a formal review for any
   non-minor changes.
2. The review process follows a similar process to ROpenSci.
3. Reviewers will be requested from associated communities.

## Retroactive commit signing

If you have pushed a commit without signing, your PR may be blocked from merging
into the `main` branch. The following steps will guide you through the process
of signing previously pushed commits. Note that you can sign multiple commits if
required.

Please take the time to understand the commands that you are using.

1. **Identify unsigned commits**

   You have a branch that contains one or more unsigned commits. Signed commits
   will be indicated by a `Verified` label, which will be absent for unsigned
   commits.
2. **Switch to the branch with unsigned commits**

   Go to your terminal and ensure that you are on the branch with the unsigned
   commits.
3. **Start an interactive rebase** by running the following command:

   ```bash
   git rebase -i main
   ```

   This puts the editor into interactive mode for rebase. You will see the
   commit history.
4. **Mark commits for editing**

   Scroll through the list until you find the commits you want to sign. Change
   the keyword `pick` to `edit` for those commits.

   If you are using `Nano`, save the changes with `Ctrl+X` and confirm with
   `Enter`. For `Vi`, exit with `:wq` to save and quit. If you are using `VS
   Code`, the commit history will open in the editor. Save with `Ctrl+S` and
   close the editor tab.
5. **Amend the commit to include a signature**

   For each commit you flagged as `edit`, run the command:

   ```bash
   git commit -S --amend --no-edit
   ```

   followed by the command:

   ```bash
   git rebase --continue
   ```

   Rebase will cycle through the commits you flagged for editing.

   Repeat the `amend` and `continue` steps for each commit.
6. **Complete the rebase**

   Once rebasing is complete, you will see a successful completion message.
7. **Push the changes**

   Push the updated commits back to your branch. Use a force push if necessary:

   ```bash
   git push -f
   ```

8. **Verify the changes**

    Refresh the browser window for your PR. You should see that the previously
    unsigned commits now have the `Verified` badge, and the merging should no
    longer be blocked.

[numpy-docs]: https://numpydoc.readthedocs.io/en/latest/format.html
