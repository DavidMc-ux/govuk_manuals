# GOVUK Manuals plugin
GOVUK Manuals plugin contains the code and templates to recreate 'hmrc internal' and 'govuk' manual guidance pages within the [GOV.UK Prototype kit](https://prototype-kit.service.gov.uk/docs/).

## How to install the plugin
1. Create a folder on your computer to store your plugins and name it 'prototype-plugins'.
2. In the terminal, use the `cd` command to navigate to the folder 'prototype-plugins' on your local computer. For example, `cd ~/Documents/projects/prototype-plugins`
3. Clone this repository into the folder using the command
```
git clone https://github.com/DavidMc-ux/govuk_manuals.git
```
4. In the terminal, navigate to the folder of your prototype that you want to use the govuk_manuals plugin with.
5. Run `npm install [path]` where `[path]` is the path to the plugin `govuk_manuals`, for example `~/Documents/projects/prototype-plugins/govuk_manuals`.

Run your prototype, the GOVUK Manuals templates should be available in the Templates section of Manage your prototype.

## Manual types and structure
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

## Add content to your manual
Use the [Govspeak guide for Whitehall publisher](https://www.gov.uk/guidance/how-to-publish-on-gov-uk/markdown) to see which content components you can use. Then use the [GOV.UK Design System](https://design-system.service.gov.uk/) to find the corresponding component's html or nunjunks.

There are some Whitehall components that are missing from the GOV.UK Design System, these will be added at a later date to this plugin. 

## Whitehall components
I've added the following Whitehall components to the plugin. Use the nunjunks code below to add them to your prototype.

### Call to action
The [call to action](https://www.gov.uk/guidance/how-to-publish-on-gov-uk/markdown#call-to-action) component is used for short links to actions, like applying for a licence. It creates a tinted box which highlights the task.

#### Nunjunks
There are two option to adding content to a call to action. 
If you only need a single paragraph with no links or text styling use the `text` variable.
```
{% from "/components/govspeak/call-to-action/macro.njk" import govspeakCallToAction %}
{{ govspeakCallToAction({
        text: 'This is a simple text paragraph. With no links or styling.'
}) }}
```
If you need to add more than one paragraph and add links, use the `html` variable.
```
{% from "/components/govspeak/call-to-action/macro.njk" import govspeakCallToAction %}
{{ govspeakCallToAction({
        html: '<p class="govuk-body">This is a <a class="govuk-link" href="https://www.gov.uk/guidance/how-to-publish-on-gov-uk/markdown#call-to-action">call to action</a> component.</p> <p class="govuk-body">It is used to highlight <strong>important information</strong> or actions that users should take. You can use it to draw attention to key messages or prompts within your content.</p>'
}) }}
```
### Addresses
The [addresses](https://www.gov.uk/guidance/how-to-publish-on-gov-uk/markdown#addresses) component is used to display addresses in content.

#### Nunjunks
Use the `html` variable to add an address. Use the html line break tag `<br>` to add line break for each line of the address.
```
 {% from "/components/govspeak/address/macro.njk" import govspeakAddress %}
{{ govspeakAddress({
        html: '<p class="govuk-body">First line of address<br>Second line of address<br>Postcode<br>Country</p>'
}) }}
```