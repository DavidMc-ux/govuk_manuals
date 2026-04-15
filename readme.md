# GOVUK Manuals plugin
GOVUK Manuals plugin contains the code and templates to recreate 'hmrc internal' and 'govuk' manual guidance pages within the [GOV.UK Prototype kit](https://prototype-kit.service.gov.uk/docs/).

## How to install the plugin
1. Create a folder on your computer to store your plugins and name it 'prototype-plugins'.
2. In the terminal, use the `cd` command to navigate to the folder 'prototype-plugins' on your local computer. For example, `cd ~/Documents/projects/prototype-plugins`
3. Clone this repository into the folder using the command
```git clone https://github.com/DavidMc-ux/govuk_manuals.git```
4. In the terminal, navigate to the folder of your prototype that you want to use the govuk_manuals plugin with.
5. Run `npm install [path]` where `[path]` is the path to the plugin `govuk_manuals`, for example `~/Documents/projects/prototype-plugins/govuk_manuals`.

Run your prototype, the GOVUK Manuals templates should be available in the Templates section of Manage your prototype.

## How to design your manual
There are two types of manual used on GOV.UK:
- HMRC internal manual (green box), see example - [Pensions Tax Manual](https://www.gov.uk/hmrc-internal-manuals/pensions-tax-manual)
- GOV.UK manual (blue box), see example - [Understanding your driving test results](https://www.gov.uk/guidance/understanding-your-driving-test-result)

Both work in a similar format with a contents page linking to several section pages:
```
|-- content page
        |-- section page one
        |-- section page two
        |-- section page three
```
An HMRC internal manual can have a sub contents page to contain a sub set of section pages:
```
|-- content page
        |-- sub contents page one
        |       |-- section page 1a
        |       |-- section page 1b
        |       |-- section page 1c
        |
        |-- section page two
        |-- section page three
```

