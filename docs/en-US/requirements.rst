Requirements Specification
===============

Non-Functional Requirements
------------------

NFR 01
^^^^^^^^^^^^^^^^^^^^^
Should run on the World Wide Web.

NFR 02
^^^^^^^^^^^^^^^^^^^^^
To develop the project, the following technologies must be used: HTML, CSS,
JavaScript, Python and Flask.

NFR 03
^^^^^^^^^^^^^^^^^^^^^
Every page must be responsive.

NFR 04
^^^^^^^^^^^^^^^^^^^^^
It should store the persistent data in a relational database.

NFR 05
^^^^^^^^^^^^^^^^^^^^^
User and month id's should be stored as a random UUID instead of ascending numbers.

NFR 06
^^^^^^^^^^^^^^^^^^^^^
It should record/traffic the user password using the bcrypt algorithm for encryption.

NFR 07
^^^^^^^^^^^^^^^^^^^^^
It should be out of order in case of ineffectiveness, returning only when repaired.

Functional Requirements
------------------

FR 01
^^^^^^^^^^^^^^^^^^^^^
The system must allow the user to log in to his account.

- The form must have the fields: ``email`` and ``password``.
- The ``email`` field must allow a minimum of 6 and a maximum of 254 characters.
- The ``password`` field must allow a minimum of 8 and a maximum of 38 characters.
- Form fields must be mandatory.
- Fields with invalid data must be highlighted.
- It should display toasts on unsuccessful attempts.
- The user must be redirected to the panel if the attempt is successful

FR 02
^^^^^^^^^^^^^^^^^^^^^
The system must allow the user to create an account.

- The form must have the following fields: ``email``, ``password`` and
  ``confirm``password``.
- The ``email`` field must allow a minimum of 6 and a maximum of 254 characters.
- The ``password`` field must allow a minimum of 8 and a maximum of 38 characters.
- The ``confirm``password`` field must allow a minimum of 8 and a maximum of 38
  characters.
- Form fields must be mandatory.
- It should display toasts on successful and unsuccessful attempts.
- The user must be redirected to the login page if the attempt is successful.

FR 03
^^^^^^^^^^^^^^^^^^^^^
The system should allow the user to add prototypes in the month.

- The form must have the fields: ``name``, ``stones``, ``made`` and ``value``.
- The ``name`` field must allow a minimum of 2 and a maximum of 32 characters.
- The ``stones`` field must limit the number to a minimum of 1 and a maximum of 400.
- The ``made`` field must limit the number to a minimum of 1 and a maximum of 300.
- The ``value`` field must only accept the values "0.025" and "0.040".
- Form fields must be mandatory.
- It should display toasts on successful and unsuccessful attempts.
- The user must be redirected to dashboard on successful and unsuccessful attempts.

FR 04
^^^^^^^^^^^^^^^^^^^^^
The system should list all prototypes added in the month.

- The data must be: ``registration date``, ``name``, ``stones``, ``value``,
  ``qty of prototypes``, ``qty of stones`` and ``profit``.

FR 05
^^^^^^^^^^^^^^^^^^^^^
The system should allow the user to remove prototypes that are added to the month.

- The user must be consulted with a confirmation before removal.
- It should display toasts on successful and unsuccessful attempts.
- The user must be redirected to dashboard on successful and unsuccessful attempts.

FR 06
^^^^^^^^^^^^^^^^^^^^^
The system should display the month summary.

- The data must be: ``month``, ``total prototypes``, ``total stones`` and ``profit``.

FR 07
^^^^^^^^^^^^^^^^^^^^^
The system should allow the user to close the month.

- The user must be consulted with a confirmation before closing.
- The user's new month must be the current month of the server if it is
  closed from day 1 to day 5.
- The user's new month must be the following server month if it is closed before
  day 1 and after day 5.
- The user cannot be allowed to end the month if the user's month is
  the following month from the server.
- It should display toasts on successful and unsuccessful attempts.
- The user must be redirected to dashboard on successful and unsuccessful attempts.

FR 08
^^^^^^^^^^^^^^^^^^^^^
The system should allow the user to share their months with other people.

- The share page should display every month of the user.
- When clicking on a month, a page should open following the requirements ``FR 04``
  and ``FR 06``.
- The user must be able to copy the link from your share page.
