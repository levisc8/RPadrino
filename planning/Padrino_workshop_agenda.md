Padrino workshop agenda
========================================================
author: Welcome!
date: 14/01/2019
autosize: true

Agenda
========================================================

- Quick update on code/digitization progress
    + Overview of challenges

- Goals for the week and goals for the long term

- Certainty in uncertainty


Updates
========================================================

- The code works!




```r
# Example from Chapter 2 of the IPM Book
oenethra_proto <- make_proto_ipm(padrino, ipm_id == 'xxxxx1')
oenethra_kernels <- make_ipm(oenethra_proto)
oenethra_k <- make_k(oenethra_kernels, oenethra_proto)

target <- 1.059307
actual <- max(Re(eigen(oenethra_k)$values))
actual - target
```

```
[1] -1.90464e-07
```

- 52 plant species and 1 very simple
Soay IPM (also Chapter 2 of the IPM book)


Long term goals
========================================================

- Database
    + Capable of storing/rebuilding any model fit with parametric statistics
    + Convey uncertainty in a clear and concise way
    + Seamless integration w/ Compadre and others

- R packages
    + `RPadrino`: Work with the data base (release  early 2020)
    + `ipmr`: Make your own IPMs! (release just before/after `Rpadrino`)
    + One or two others to assist with maintenance/digitization (not user facing)

- Papers
    + Introduction to `Rpadrino` and `ipmr`
    + How to report your own IPMs
    + ...

- Website (late 2019  (?))
    + Need to recruit for this, not really something I have time for or am any good at

- Mirrors (coinciding w/ first release)
    + Multiple mirrors to ensure that work can continue even if a given node temporarily goes offline


Goals for the week
========================================================

- Monday AM (all)
    + How to deal with/store/re-construct uncertainty in IPMs


        + Storage


        + Reporting


        + User-facing functionality


- Monday PM (breakouts)
    + Sketching out the rest of user-facing functionality
        + What does every function return?


    + First 5 papers enumerated w/ divisions of labor (Aim for the stars!!)
        + Opt-out model for those in the room right now

    + Finish with a 10-15 minute progress update from each group


Goals for the week
========================================================

- Tuesday  AM (breakouts)
    + Recap

    + Sketching out the rest of user-facing functionality
        + What does every function return?

    + First 5 papers enumerated w/ divisions of labor (Aim for the stars!!)
        + Opt-out model for those in the room

- Tuesday PM
    + Possibly more functionality/implementation details

    + sApropos (while we're all here still?)

    + Finish with a 10-15 minute progress update from each group


Goals for the week
========================================================

- Wednesday (all)
    + Fun admin stuff!!
        + New members
        + Hosting

    + Tidying up loose ends/recap

    + Dealing with other matters that have come up in the course of discussions

