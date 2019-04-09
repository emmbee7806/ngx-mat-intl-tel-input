# International Telephone Input for Angular Material (NgxMatIntlTelInput)

An Angular Material package for entering and validating international telephone numbers. It adds a flag dropdown to any input, detects the user's country, displays a relevant placeholder and provides formatting/validation methods.

**Supports:**

- Angular 7
- Angular Material 7
- ReactiveFormsModule
- FormsModule
- Validation with [google-libphonenumber](https://github.com/ruimarinho/google-libphonenumber)

## Installation

### Install Dependencies

```$ npm install google-libphonenumber --save```

### Install This Library

```$ npm install ngx-mat-intl-tel-input --save```

## Usage

### Import

Add ```NgxIntlTelInputModule``` to your module file:

```javascript

imports: [
    NgxIntlTelInputModule,
  ]

```

## Example

Refer to main app in this repository for working example.

```html

<form #f="ngForm" [formGroup]="phoneForm">
  <ngx-mat-intl-tel-input
  [cssClass]="'custom'"
  [preferredCountries]="['us', 'gb']"
  [onlyCountries]="['us', 'gb', 'es']"
  [enableAutoCountrySelect]="true"
  [enablePlaceholder]="true"
  name="phone"
  formControlName="phone"></ngx-mat-intl-tel-input>
</form>

```

If you want to show the sample number for the country selected or errors , use mat-hint anf mat-error as

```html
<form #f="ngForm" [formGroup]="phoneForm">
  <ngx-mat-intl-tel-input
    [cssClass]="'custom'"
    [preferredCountries]="['us', 'gb']"
    [onlyCountries]="['us', 'gb', 'es']"
    [enableAutoCountrySelect]="true"
    [enablePlaceholder]="true"
    name="phone"
    formControlName="phone" #phone></ngx-mat-intl-tel-input>
  <mat-hint>e.g. {{phone.selectedCountry.placeHolder}}</mat-hint>
  <mat-error *ngIf="f.form.controls['phone']?.errors?.required">Required Field</mat-error>
  <mat-error *ngIf="f.form.controls['phone']?.errors?.validatePhoneNumber">Invalid Number</mat-error>
</form>
```

## Options

| Options                       | Type                   | Default            | Description                                                                         |
| ------------------------------|------------------------|--------------------|-------------------------------------------------------------------------------------|
| preferredCountries            | ```string[]```         | ```[]```           | List of country abbreviations, which will appear at the top.                        |
| onlyCountries                 | ```string[]```         | ```[]```           | List of manually selected country abbreviations, which will appear in the dropdown. |                    |
| enablePlaceholder             | ```boolean```          | ```true```         | Input placeholder text, which adapts to the country selected.                      |

## Library Contributions

- Fork repo.
- Go to ```./projects/ngx-mat-intl-tel-input```
- Update ```./src/lib``` with new functionality.
- Update README.md
- Pull request.

### Helpful commands

- Build lib: ```$ npm run build_lib```
- Copy license and readme files: ```$ npm run copy-files```
- Create package: ```$ npm run npm_pack```
- Build lib and create package: ```$ npm run package```

### Use locally

After building and creating package, you can use it locally too.

In your project run:

```$ npm install --save {{path to your local '*.tgz' package file}}```
