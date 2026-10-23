# DCC schools list

This file, `dcc_schools.csv`, is the list of schools that appears as suggestions on the Dymocks Children's Charities Programs EOI form:

https://www.dymockschildrenscharities.org.au/programs-eoi

When someone chooses **School** and starts typing their school's name, the form looks up this file and fills in the address for them.

The form reads the file straight from here, so any change you save on GitHub shows on the form within about 5 minutes. There's nothing to change on the website.

## The golden rules

1. **Edit or add rows in the existing file. Never replace it with a Salesforce export** or any other spreadsheet. Exports have different columns and the lookup will stop working.
2. **Keep the five column headings exactly as they are**, in the first row:

   `school_name,street,suburb,state,postcode`

3. **State** must be one of: `ACT`, `NSW`, `NT`, `QLD`, `SA`, `TAS`, `VIC` or `WA`. Not "New South Wales" or "N.S.W.".
4. **Postcode** must be 4 digits, for example `2000` or `0870`.
5. **School names must match the organisation name in Salesforce exactly**, letter for letter, including capitals, apostrophes and anything after a dash. The form sends the name exactly as it appears in this file, and that's how submissions are matched to Salesforce organisation records.
6. **Keep the file name `dcc_schools.csv`.**

It's fine to leave street, suburb, state or postcode blank if you don't have them. The form fills in what's there and asks the person to type the rest.

## If something goes wrong

A mistake in this file can never break the form itself.

- A row with a bad state or postcode, or no school name, is skipped. That school just won't appear as a suggestion.
- If the column headings are changed or the file can't be read, the suggestions switch off and people type their school's details in by hand, exactly as they did before the lookup existed.

So if a school isn't appearing, check its row against the rules above.

## How to edit the file

**To change a few rows**, you can do it right here on GitHub:

1. Click `dcc_schools.csv` in the file list above.
2. Click the pencil icon ("Edit this file").
3. Make your change. Each line is one school, with commas between the five values. If a value contains a comma, wrap the whole value in double quotes.
4. Click **Commit changes**, add a short note (for example "Added Smithtown Primary School"), and confirm.

**To make lots of changes**, use a spreadsheet:

1. Click `dcc_schools.csv`, then click the download button ("Download raw file").
2. Open it in Excel or Google Sheets, then edit or add rows. Don't delete or rename the heading row.
3. **Excel warning:** Excel removes the leading zero from NT and ACT postcodes (`0870` becomes `870`). Before saving, select the postcode column, set its format to Text, and put any missing zeros back.
4. Save it as **CSV UTF-8**, named exactly `dcc_schools.csv`.
5. Back on this page, click **Add file**, then **Upload files**, drag in your `dcc_schools.csv`, add a short note, and click **Commit changes**.

After about 5 minutes, open the EOI form, choose **School**, and type the name of a school you changed to check it appears correctly.

## Where the list came from

The list was built from the Australian Schools List (https://asl.acara.edu.au/school-search) and the client's own school data. Some schools have no street on file on purpose, and a few have no postcode or state. When one of those is chosen, the form asks the person to type in the missing details.
