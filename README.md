# Algorand Error Handling Git Bounty Proposal

### Ritchel Cousar Jr. - https://github.com/overhead525

### Link to Gitcoin Bounty: [Improve Error And Update Handling For Algorand Sandbox [$750]](https://gitcoin.co/issue/algorandfoundation/grow-algorand/30/100025839)

<br>

<html>
  <style>
    img.logo {
      margin-bottom: 1rem;
    }
  </style>
  <img alt="Algorand Algo Logo" src="algorand-algo-logo.png" width=50 class="logo" />
</html>

---
<br>

### Table of Contents

[Abstract](#abstract)\
[Work Plan](#work-plan)\
[Questions I Have For You](#questions-i-have-for-you)\
[About Me](#about-me)\
[Discussion and PRs](#discussions-and-prs)

<br>

## Abstract

&emsp;The sandbox at https://github.com/algorand/sandbox is used to create a development environment for users who want to test applications that make use of Algorand. The purpose of their application isn't really important here. But what is important, is their ability to update parts of the 
development environment *or lack thereof, currently*.

&emsp;Upon closer inspection of the code, I understand the sandbox to basically be a shell script that
spins up three docker containers on the user's local machine using `docker-compose`, along with various
options and commands. *I won't lie, I had a lot of fun exploring the code. Excellent architecture.*

<br>

<image alt="Algorand Sandbox Diagram" src="algorand-sandbox-diagram.png" width=500 />

## Work Plan
There are three requirements for this bounty:
1.  **Update algod/indexer during** `./sandbox up`
2.  Force rebuild after cleaning
3.  Improve error handling

Here's how I plan to work on them:

<html>
  <head>
    <style>
      text {
        font-family: sans-serif !important;
      }
    </style>
    <script
      type="text/javascript"
      src="https://www.gstatic.com/charts/loader.js"
    ></script>
    <script type="text/javascript">
      google.charts.load("current", { packages: ["gantt"] });
      google.charts.setOnLoadCallback(drawChart);

      function daysToMilliseconds(days) {
        return days * 24 * 60 * 60 * 1000;
      }

      function drawChart() {
        var data = new google.visualization.DataTable();
        data.addColumn("string", "Task ID");
        data.addColumn("string", "Task Name");
        data.addColumn("string", "Resource");
        data.addColumn("date", "Start Date");
        data.addColumn("date", "End Date");
        data.addColumn("number", "Duration");
        data.addColumn("number", "Percent Complete");
        data.addColumn("string", "Dependencies");

        data.addRows([
          [
            "Research",
            "Explore the Repository",
            "Research",
            new Date(2021, 5, 8, 20),
            new Date(2021, 5, 9),
            null,
            100,
            null,
          ],
          [
            "Planning Issues 1 and 2",
            "Plan Solutions and Ask Questions 1 and 2",
            "Planning",
            new Date(2021, 5, 9, 12),
            new Date(2021, 5, 9, 20),
            null,
            50,
            null,
          ],
          [
            "Issue 1",
            "Implement Solution for Issue 1",
            "Implementation",
            new Date(2021, 5, 10, 8),
            new Date(2021, 5, 10, 12),
            null,
            0,
            null,
          ],
          [
            "Submission Issue 1",
            "Submit PR Request for Issue 1",
            "Submission",
            new Date(2021, 5, 10, 12),
            new Date(2021, 5, 10, 12, 30),
            null,
            0,
            null,
          ],
          [
            "Issue 2",
            "Implement Solution for Issue 2",
            "Implementation",
            new Date(2021, 5, 10, 16),
            new Date(2021, 5, 10, 20),
            null,
            0,
            null,
          ],
          [
            "Submission Issue 2",
            "Submit PR Request for Issue 2",
            "Submission",
            new Date(2021, 5, 10, 20),
            new Date(2021, 5, 10, 20, 30),
            null,
            0,
            null,
          ],
          [
            "Planning",
            "Plan Solutions and Ask Question 3",
            "Planning",
            new Date(2021, 5, 11, 8),
            new Date(2021, 5, 11, 12),
            null,
            0,
            null,
          ],
          [
            "Issue 3",
            "Implement Solution for Issue 3",
            "Implementation",
            new Date(2021, 5, 12, 8),
            new Date(2021, 5, 12, 12),
            null,
            0,
            null,
          ],
          [
            "Submission Issue 3",
            "Submit PR Request for Issue 3",
            "Submission",
            new Date(2021, 5, 12, 12),
            new Date(2021, 5, 12, 12, 30),
            null,
            0,
            null,
          ],
        ]);

        var options = {
          height: 500,
          width: 1000,
          fontName: "Roboto",
        };

        var chart = new google.visualization.Gantt(
          document.getElementById("chart_div")
        );

        chart.draw(data, options);
      }
    </script>
  </head>
  <body>
    <div id="chart_div"></div>
  </body>
</html>

## About Me
**My Local Setup:** Windows running WSL2 (Ubuntu 18.04 LTS)

&emsp;I understand that you want the solution tested on Ubuntu 20.04 and MacOSX as well, so I'll spin up
a couple of docker instances to test those operating systems.

## Questions I Have For You
[**Question 1:**](https://github.com/overhead525/algorand-error-handling/issues/1) In the bounty description, you mentioned that the `README.md` file in the `algorand/sandbox` repository needed to be update. That's cool. But you also mentioned the phrase *other user-facing documentation*. Is this documentation in another repository? I could use some help identifying where I need to change things. It would save some time.

...

## Discussions and PRs
...

