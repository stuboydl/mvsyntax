# mvsyntax

## 🚀 Welcome to the MVSyntax Repository

This repository is a collection of miscellaneous multivalue database system syntaxes and grammars. It aims to provide resources to work with various development tools effectively.

It is a work in progress. if you feel something is missing or incorrect please [get involved](#get_involved).

## Topics Covered

The repository covers a range of topics related to multivalue database syntaxes and grammars. Some of the key topics included are:

- Beyond-Compare
- Linguist
- Rocket Software
  - UniVerse
  - UniData
  - jBase
  - D3
- Visual Studio Code

See the Rocket Software website for more information on UniVerse, UniData, jBase, D3, mvBase, OpenQM and multivalue in general here <https://www.rocketsoftware.com/products/rocket-multivalue-application-development-platform/all-products>
Documentation <https://docs.rocketsoftware.com>
Forums <https://community.rocketsoftware.com/home>

## Beyond Compare

[Beyond Compare](https://www.scootersoftware.com/) is a commercial utility for comparing, diffing, merging, and synchronizing files and folders. It supports various environments, file types, syntax highlighting, filters, and scripting.

The BCFileFormats.xml file may be imported into Beyond Compare to provide syntax highlighting and comparison rules for mvBasic and mv data.

![bc sample](beyond-compare/bcsample.png)

## Linguist

The Linguist library is used on GitHub.com to detect blob languages, ignore binary or vendored files, suppress generated files in diffs, and generate language breakdown graphs.

When committing any mvBasic to GitHub, Use `* linguist-language=mvBasic` in your `.gitattributes` file to explicitly indicate the language is mvBasic.

As most mvBasic files don't have any specific identifier, such as a well-known filename extension or header _shebang_ line [although the _SUBROUTINE/PROGRAM_ keywords may be taken into consideration??], using this enables Linguist to identify the language type.

By specifying the associated file types in the `.gitattributes` file, Linguist will use that to explicitly identify miscellaneous files.

For example, if you have both Python and mvBasic files in your main branch, you can identify Python code by its extension and everything else as mvBasic:

> `# Example of a '.gitattributes' file which classifies '.py' files as Python and everything else as mvBasic:`
> `*.py linguist-language=python`
> `* linguist-language=mvbasic`

If Linguist doesn't have anything else to go by it will use heuristics and naïve Bayesian classification to attempt to identify the file type.

## Rocket Software

## Visual Studio Code

[VS Code](https://visualstudio.microsoft.com/#vscode-section) is a free standalone source code editor that runs on Windows, macOS, and Linux. The top pick for mvBasic developers, with extensions to support most programming languages and a vast range of utility extensions.

This opens mv programming to the world of modern programming editing tools and utilities including AI assistants that work with MV environments.

Recommended extensions include:

* [mv Basic](https://marketplace.visualstudio.com/items?itemName=MVExtensions.mvbasic) - mvBasic programming syntax and utilities.
* [Pickdate!](https://marketplace.visualstudio.com/items?itemName=stuboydl.vscode-pickdate) - _Pick_ internal date & time.
* [Better align](https://marketplace.visualstudio.com/items?itemName=Chouzz.vscode-better-align) - select and align code.
* [Remote - SSH](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-ssh) extension for accessing your code base through SSH.
* [Github Copilot](https://marketplace.visualstudio.com/items?itemName=GitHub.copilot) - AI assistant.

## Keywords

- Beyond Compare
- D3
- Database
- DBMS
- Grammar
- Grammar Rules
- Linguist
- MultiValue
- MV
- MVBasic
- Pick
- Pick Basic
- PickBasic
- Rocket
- U2
- UniData
- Universe
- VSCode

## Helpful Resources

In this repository, you will find resources including syntax and grammar guides, complete grammars and sample code snippets. Feel free to explore the contents.

## Get Involved

If you are passionate about multivalue databases and syntaxes, I welcome your contributions to this repository. Whether you want to suggest improvements, add new syntax examples, or share your knowledge, your input is gratefully accepted and highly valued.

### TODO add contribution guideline doc

#### **Did you find a bug?**

- **Ensure the bug was not already reported** by searching on GitHub under [Issues](https://github.com/stuboydl/mvsyntax/issues).

- If you're unable to find an open issue addressing the problem, [open a new one](https://github.com/stuboydl/mvsyntax/issues/new). Be sure to include a **title and clear description**, as much relevant information as possible, and a **code sample** or an **executable test case** demonstrating the expected behavior that is not occurring.

<!-- - If possible, use the relevant bug report templates to create the issue. Simply copy the content of the appropriate template into a .rb file, make the necessary changes to demonstrate the issue, and **paste the content into the issue description**:
  * [**Active Record** (models, encryption, database) issues](https://github.com/rails/rails/blob/main/guides/bug_report_templates/active_record.rb)
  * [**Active Record Migrations** issues](https://github.com/rails/rails/blob/main/guides/bug_report_templates/active_record_migrations.rb)
  * [**Action View** (views, helpers) issues](https://github.com/rails/rails/blob/main/guides/bug_report_templates/action_view.rb)
  * [**Active Job** issues](https://github.com/rails/rails/blob/main/guides/bug_report_templates/active_job.rb)
  * [**Active Storage** issues](https://github.com/rails/rails/blob/main/guides/bug_report_templates/active_storage.rb)
  * [**Action Mailer** issues](https://github.com/rails/rails/blob/main/guides/bug_report_templates/action_mailer.rb)
  * [**Action Mailbox** issues](https://github.com/rails/rails/blob/main/guides/bug_report_templates/action_mailbox.rb)
  * [**Action Pack** (controllers, routing) issues](https://github.com/rails/rails/blob/main/guides/bug_report_templates/action_controller.rb)
  * [**Generic template** for other issues](https://github.com/rails/rails/blob/main/guides/bug_report_templates/generic.rb)

* For more detailed information on submitting a bug report and creating an issue, visit our [reporting guidelines](https://edgeguides.rubyonrails.org/contributing_to_ruby_on_rails.html#reporting-an-issue).

#### **Did you write a patch that fixes a bug?**

- Open a new GitHub pull request with the patch.

- Ensure the PR description clearly describes the problem and solution. Include the relevant issue number if applicable.

- Before submitting, please read the guide [_TODO_] to know more about coding conventions and benchmarks.

#### **Did you fix whitespace, format code, or make a purely cosmetic patch?**

Changes that are cosmetic in nature and do not add anything substantial to the stability, functionality, or testability of syntaxes and grammars will generally not be accepted (read more about [our rationales behind this decision](https://github.com/rails/rails/pull/13771#issuecomment-32746700)).

#### **Do you intend to add a new feature or change an existing one?**

- Suggest your change and start writing code

- Do not open an issue on GitHub until you have collected positive feedback about the change. GitHub issues are primarily intended for bug reports and fixes

* We generally reject changes to Active Support core extensions. Those change should be proposed in the [Ruby issue tracker instead](https://bugs.ruby-lang.org/issues), as we don't want to conflict with future versions of Ruby.

#### **Do you have questions about the source code?**

- Ask any question about how to use MV in the [mv forums](https://community.rocketsoftware.com/home).

#### **Do you want to contribute to this documentation?**

- Please read [Contributing to the mvsyntax Documentation](https://example.com)

MVSyntax is a volunteer effort. We encourage you to pitch in and join [the team](https://example.com)!

Thanks! :heart: :heart: :heart:

MvSyntax Team -->

## Stay Updated

To stay updated with the latest developments and additions to the MVSyntax repository, be sure to watch this repository. By watching the repository, you will receive notifications about new releases, code updates, and community contributions.

## Connect

For any questions, suggestions, or collaboration opportunities, feel free to reach out to me via Rocket forums. Your feedback is crucial in improving this repository and making it a valuable resource for the multivalue community.

Thank you for visiting the MVSyntax repository. Happy exploring and coding with multivalue databases! 🌟🚀
