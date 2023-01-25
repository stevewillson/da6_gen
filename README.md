# da6_gen

## Installation

There are two ways to obtain the `da6_gen` files, downloading the `.zip` archive or using `git` (https://git-scm.com/).

### Method 1: Downloading the `.zip` archive

Click `Code` > `Download ZIP`.

Unzip the downloaded file.

Use a web browser to open the `index.html` file.

### Method 2: Downloading with `git`

Clone the git repository: `git clone https://github.com/stevewillson/da6_gen`.

Change the directory to the `da6_gen` folder: `cd da6_gen`.

Use a web browser to open the `index.html` file.

## Usage: Generate a DA6 Duty Roster

Create a Comma Separated Value (`.csv`) file, use the example `da6.csv` as a reference.

Upload the `.csv` file with the following columns:

`Rank, Name, Days Since Last`

Click `Generate DA6 Roster` to produce an interactive DA6. The generated DA6 can be copied to Excel for easy printing.

Each cell is 'clickable' to change the Soldier's status during that day between:
Available, 'A', 'D', or 'U'. See AR 220-45 for the meaning of these designators.

From AR 220-45

(1) Soldiers who are absent or otherwise not available because of leave, pass, special duty, temporary duty, illness in line of duty, or any other authorized reason (not due to misconduct) will be indicated by the letter "A." When a new DA Form 6 is initiated that carries over a nonchargeable status from the previous DA Form 6, a superscript number (for example, A3) will be manually added to the abbreviation "A" to indicate the last number charged, as shown on the previous DA Form 6, before the Soldier entered upon the nonchargeable status. Entering such a number in the first column of a new DA Form 6 eliminates the necessity for referring to the previous DA Form 6 when the Soldier returns to a chargeable status. Note. Soldier on temporary duty travel that does not extend beyond regular duty hours will not qualify for an "A" for that day of temporary duty.

(2) Soldiers eligible for detail who could not be selected because of previous detail or other duty will be indicated by the letter "D."

(3) Soldiers not available because of being absent without leave, in arrest, in confinement, illness not in line of duty, or otherwise not available as a result of their own misconduct will be indicated by the letter "U."

## Configuration options

- Set the 'Nature of Duty', 'Organization', and 'From Date'
- Can set the start day (the end day will be 39 days after the start (for a total of 40 columns)

## Future

### Configuration Options

- Select different counts for weekends and weekdays
- Ingest AAA-162 formatted rosters
- Allow a custom date range
- Allow to select non-consecutive dates
- Provide an output for the end of the roster status, allowed to be used for the next roster

### UI Enhancement

- 'Drag and drop' duty days
- Create a roster from a list of people
- Specify that a Soldier will have duty on a particular day, create the roster around these custom specifications

## Technical Details

The data structure of the 'da6_pers_list' is the following

- Rank
- Name
- Duty
  -- date: yyyy-mm-dd
  -- daysSinceLastDuty: Number
  -- dutyStatus: Number or Letter

The 'dutyStatus' is either the days since the last duty (if the Soldier is available for duty) or the 'A', 'U', or 'D'
