# Tidy-Up-MUnit-Recording

[MUnit test recordings](https://docs.mulesoft.com/munit/latest/test-recorder) are an nice feature for automating and enhancing testing  in MuleSoft applications. They streamline the creation of test cases by automatically capturing flow inputs, outputs, and mock configurations. However, while the recordings provide a foundation for testing, they often result in output that can be somewhat messy — with numerous files that can make tests hard to read and maintain. Additionally, the generated filenames often lack meaningful descriptors, making it difficult to understand their purpose or content at a glance.

`Tidy-Up-MUnit-Recording` is a script designed to tackle this very problem. It cleans up MUnit test recordings by allowing users to inline content from external files, rename file references, edit the referenced files, or delete unnecessary content. This tool aims to produce a cleaner, more organized, and thus more maintainable test suite.


## Features

- **Inline Content**: Inlines DWL content from external files into the MUnit test XML.
- **Rename References**: Provides an easy way to rename file references and automatically suggesting better filenames.
- **Delete Content**: Offers the option to delete specific content from the test files that are no longer needed.
- **Edit Content**: Offers the option to edit the content of the referenced file
- **Interactive Prompts**: Utilizes an interactive CLI to guide users through the tidying process with clear options for each detected external reference.
- **Backup Creation**: Automatically creates a backup of the original test file before applying any changes.

## Prerequisites

Before you begin, ensure you have the following requirements:
- Ruby (version 2.5 or later)
- The following Ruby gems:
  - `rexml`
  - `tty-prompt`
  - `rouge`
  - `fileutils`

You can install the required gems using the following command:

```
gem install tty-prompt rouge fileutils
```

## Usage

1. Clone the repository or download the `tidy-up-munit-recording` script to your local machine.
2. Ensure the script is executable:
   
   ```
   chmod +x tidy-up-munit-recording
   ```

3. Run the script, passing the path to the MUnit test file as an argument:

   ```
   tidy-up-munit-recording path/to/your/munit_test_file.xml
   ```

The script will automatically process the specified MUnit test file, prompting you at each step for actions to take on external references and elements within the file.

To tidy-up a specific test, you can pass the test name as an argument:

   ```
   tidy-up-munit-recording path/to/your/munit_test_file.xml test_name
   ```

## Caveats

### Filename Suggestions

The effectiveness of the filename suggestions provided by `Tidy-Up-MUnit-Recording` is directly linked to the quality of `doc:name` attributes within your MUnit tests and, by extension, the `doc:name` attributes in your MuleSoft application code. These suggestions are generated based on the `doc:name` attribute of each test, which ideally should be reflective of the test's purpose and contents.

### Editor Compatibility
The "E" (Edit) option relies on the `EDITOR` environment variable to determine the preferred text editor. If `EDITOR` is not set, it defaults to `notepad` on Windows and `nano` on Unix/Linux. Ensure your preferred editor is set correctly in your environment for the best experience.


## Contributing

Contributions to `Tidy-Up-MUnit-Recording` are welcome! If you have suggestions for improvements or encounter any issues, please feel free to open an issue or submit a pull request.

## License

This project is licensed under the [MIT License](LICENSE.md) - see the LICENSE file for details.

## Acknowledgments

- MUnit and MuleSoft are trademarks of MuleSoft LLC, a Salesforce company.


## TODO
