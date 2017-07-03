angular-cron-gen
===================

A basic way to for users to graphically build a cron expression.

Demo can be found [here](https://vincentjames501.github.io/angular-cron-gen/).

**Requirements:** AngularJS 1.5+

## Usage:

1. Include the dependency in your app

    ```js
    angular.module('myApp', ['angular-cron-gen'])
    ```

2. Include the supplied JS and CSS file (or create your own CSS to override defaults).

    ```html
    <link rel='stylesheet' href='build/cron-gen.min.css' type='text/css' media='all' />
    <script type='text/javascript' src='build/cron-gen.min.js'></script>
    ```

3. That's it -- you're done!

#### Via bower:
```
$ bower install angular-cron-gen
```
#### Via npm:
```
$ npm install angular-cron-gen
```

## Options

```html
<cron-gen ng-model="cronExpression" 
          options="cronOptions" 
          template-url="your optional, custom template (Defaults to a bootstrap 3 template)"
          cron-format="quartz (Currently only compatible with 'quartz' and defaults to 'quartz')"
          ng-disabled="isCronDisabled"
          locale="en_US (current locale - dafults to 'en_US')"
          locale-path="i18n/ (path to locale folder - dafults to 'i18n/')">
</cron-gen>
```

```js
angular.module('myApp', ['angular-cron-gen'])
  .controller('myController', ['$scope', ($scope) => {
    $scope.cronExpression = '0 0 0/3 1/1 * ? *';
    $scope.isCronDisabled = false;
    $scope.cronOptions = {
      formInputClass: 'form-control cron-gen-input', // Form input class override
      formSelectClass: 'form-control cron-gen-select', // Select class override
      formRadioClass: 'form-control-static cron-gen-radio', // Radio class override
      formCheckboxClass: 'form-control-static cron-gen-checkbox', // Radio class override
      hideMinutesTab: false, // Whether to hide the minutes tab
      hideHourlyTab: false, // Whether to hide the hourly tab
      hideDailyTab: false, // Whether to hide the daily tab
      hideWeeklyTab: false, // Whether to hide the weekly tab
      hideMonthlyTab: false, // Whether to hide the monthly tab
      hideYearlyTab: false, // Whether to hide the yearly tab
      hideAdvancedTab: true, // Whether to hide the advanced tab
      use24HourTime: false, // Whether to show AM/PM on the time selectors
      hideSeconds: false // Whether to show/hide the seconds time picker
    };
  }])
```

## Locales
This is the json file needed to have translations.
```json
{
  "DAY_LOOKUPS": {
    "SUN": "Sunday",
    "MON": "Monday",
    "TUE": "Tuesday",
    "WED": "Wednesday",
    "THU": "Thursday",
    "FRI": "Friday",
    "SAT": "Saturday"
  },
  "MONTH_WEEK_LOOKUPS": {
    "#1": "First",
    "#2": "Second",
    "#3": "Third",
    "#4": "Fourth",
    "#5": "Fifth",
    "L": "Last"
  },
  "MONTH_LOOKUPS": {
    "1": "January",
    "2": "February",
    "3": "March",
    "4": "April",
    "5": "May",
    "6": "June",
    "7": "July",
    "8": "August",
    "9": "September",
    "10": "October",
    "11": "November",
    "12": "December"
  },
  "MONTHDAY_LOOKUPS": {
    "1": "1st day",
    "2": "2nd day",
    "3": "3rd day",
    "4": "4th day",
    "5": "5th day",
    "6": "6th day",
    "7": "7th day",
    "8": "8th day",
    "9": "9th day",
    "10": "10th day",
    "11": "11th day",
    "12": "12th day",
    "13": "13th day",
    "14": "14th day",
    "15": "15th day",
    "16": "16th day",
    "17": "17th day",
    "18": "18th day",
    "19": "19th day",
    "20": "20th day",
    "21": "21st day",
    "22": "22nd day",
    "23": "23rd day",
    "24": "24th day",
    "25": "25th day",
    "26": "26th day",
    "27": "27th day",
    "28": "28th day",
    "29": "29th day",
    "30": "30th day",
    "31": "31st day",
    "L": "Last Day",
    "LW": "Last Weekday",
    "1W": "First Weekday"
  },
  "TABS": {
    "MINUTES": "Minutes",
    "HOURLY": "Hourly",
    "DAILY": "Daily",
    "WEEKLY": "Weekly",
    "MONTHLY": "Monthly",
    "YEARLY": "Yearly",
    "ADVANCED": "Advanced"
  },
  "LABELS": {
    "ONTHE": "on the",
    "EVERY": "every",
    "MINUTES": "minute(s)",
    "ON_SECOND": "on second",
    "HOUR_ON_MINUTE": "hour(s) on minute",
    "AND_SECOND": "and second",
    "DAY_AT": "day(s) at",
    "EVERY_WEEKDAY": "every week day (Monday through Friday) at",
    "START_TIME": "start time",
    "OF_EVERY": "of every",
    "MONTH_AT": "month(s) at",
    "AT": "at",
    "OF": "of",
    "CRON_EXPRESSION": "Cron Expression",
    "CRON_DETAILS": "More details about how to create these expressions can be found",
    "CRON_HERE": "here"
  }
}
```

## License:
Licensed under the MIT license
