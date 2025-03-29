## Conventional Commits Guide

Conventional Commits is a specification that standardizes the format of commit messages. It improves clarity and facilitating automation in project management. By adhering to this convention, teams can produce a consistent and readable commit history, which is particularly beneficial for generating changelogs, automating versioning, and streamlining collaboration. For what it's worth, there is also something aesthetically pleasing about conventional commits.

### Commit Message Structure

A Conventional Commit message consists of the following components:

1. **Header**: Contains the type, optional scope, and a concise description of the change.
2. **Body** (optional): Provides a more detailed explanation of the change, including the motivation behind it and how it differs from previous implementations.
3. **Footer** (optional): Includes any metadata related to the commit, such as issue references or breaking changes.

The general format is:

```
<type>[optional scope]: <description>

[optional body]

[optional footer(s)]
```


**Example:**

```
feat(auth): add OAuth2 login capability

Implemented OAuth2 authentication to enhance security and user convenience. This includes support for authorization code flow and token management.

BREAKING CHANGE: The old authentication method using API keys has been removed. All clients must now use OAuth2.
```


### Common Commit Types

The following are standard types used in Conventional Commits:

- **feat**: Introduces a new feature.
- **fix**: Addresses a bug fix.
- **docs**: Pertains to documentation changes.
- **style**: Involves code style adjustments (e.g., formatting) without affecting functionality.
- **refactor**: Refactors code without adding features or fixing bugs.
- **test**: Adds or modifies tests.
- **chore**: Updates build processes or auxiliary tools and libraries.


### Specific Grammar Rules

When crafting commit messages, adhere to the following grammatical conventions:

- **Use the imperative mood**: Write the description as if giving a command, e.g., "add feature" instead of "added feature" or "adds feature."
- **Limit the header length**: Keep the header line to a maximum of 72 characters.
- **Do not capitalize the first letter**: The description should start with a lowercase letter unless it begins with a proper noun or acronym.
- **Avoid punctuation at the end of the header**: Do not end the header line with a period.


### Body and Footer Sections

While the header provides a succinct summary, the body and footer sections allow for more detailed information:

- **Body**: Begin with a blank line after the header. Elaborate on the change, its rationale, and any additional context. The body can span multiple paragraphs if necessary.

- **Footer**: Start with a blank line after the body. Include metadata such as issue trackers, co-authors, or important notes. Each piece of metadata should be on its own line.

**Example:**

```
fix(parser): handle null values in input

Previously, the parser would throw an error when encountering null values. This fix ensures that null values are handled gracefully by returning an empty string.

Fixes #42
```


By following these guidelines, commit messages become more structured and informative, aiding both current project maintenance and future development efforts. For a comprehensive guide on Conventional Commits, refer to the [official specification](https://www.conventionalcommits.org/en/v1.0.0/).

