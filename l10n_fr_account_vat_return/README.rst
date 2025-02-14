=================
France VAT Return
=================

.. !!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!
   !! This file is generated by oca-gen-addon-readme !!
   !! changes will be overwritten.                   !!
   !!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!

.. |badge1| image:: https://img.shields.io/badge/maturity-Beta-yellow.png
    :target: https://odoo-community.org/page/development-status
    :alt: Beta
.. |badge2| image:: https://img.shields.io/badge/licence-AGPL--3-blue.png
    :target: http://www.gnu.org/licenses/agpl-3.0-standalone.html
    :alt: License: AGPL-3
.. |badge3| image:: https://img.shields.io/badge/github-OCA%2Fl10n--france-lightgray.png?logo=github
    :target: https://github.com/OCA/l10n-france/tree/14.0/l10n_fr_account_vat_return
    :alt: OCA/l10n-france
.. |badge4| image:: https://img.shields.io/badge/weblate-Translate%20me-F47D42.png
    :target: https://translation.odoo-community.org/projects/l10n-france-14-0/l10n-france-14-0-l10n_fr_account_vat_return
    :alt: Translate me on Weblate
.. |badge5| image:: https://img.shields.io/badge/runbot-Try%20me-875A7B.png
    :target: https://runbot.odoo-community.org/runbot/121/14.0
    :alt: Try me on Runbot

|badge1| |badge2| |badge3| |badge4| |badge5| 

This module adds support for the French VAT declaration *CA3* (monthly or quarterly):

* computation of the boxes of the CA3 form,
* print the CA3 PDF,
* auto-fill the CA3 form on impots.gouv.fr,
* generate the corresponding journal entry.

It can also be used for the smaller companies which have a yearly CA12 VAT declaration. But, for CA12, the generation of the PDF and the auto-fill of the form on impots.gouv.fr is not supported: you will have to manually copy the values on the online form.

This module also supports declaration 3519 for the reimbursement of VAT credit.

AFAIK, this module is the only solution which proposes a free tele-transmission of the CA3 via the auto-fill of the CA3 form on impots.gouv.fr. All the other CA3 tele-transmission solutions are not free. For that, this module relies on `Selenium IDE <https://www.selenium.dev/selenium-ide/>`_, which is a plugin available for Firefox and Chrome. Selenium is a free-software project initially designed to test Websites.

The following boxes of the CA3 form are natively supported by this module:

* 04: **Exportations hors CE** : Odoo selects the *Extra-EU* fiscal positions, gets the destination account of the account mapping and sums the period balance of each destination account.
* 5A: **Ventes à distance taxables dans un autre État membre au profit des personnes non assujetties – Ventes B to C**: Odoo selects the *Intra-EU B2C over 10k€ limit* fiscal positions, gets the destination account of the account mapping and sums the period balance of each destination account.
* 06: **Livraisons intracommunautaires à destination d'une personne assujettie - Ventes B to B**: Odoo selects the *Intra-EU B2B* fiscal positions, gets the destination account of the account mapping and sums the period balance of each destination account.

**Table of contents**

.. contents::
   :local:

Usage
=====

Click on the button

* Odoo will generate a scenario file for Selenium IDE,
* in your web browser, click on the icon corresponding to Selenium IDE and load in the Selenium IDE file
* it will start a new web browser window that will connect to impots.gouv.fr
* enter your credentials for impots.gouv.fr and then the scenario will continue it's execution until the selection of the form
* select the form corresponding to the VAT period
* Odoo will fill-up all the boxes of the CA3 form with the values computed by Odoo
* Validate and form and confirm it
* Follow the process to make the corresponding payment (unless if your company has a VAT credit).

Bug Tracker
===========

Bugs are tracked on `GitHub Issues <https://github.com/OCA/l10n-france/issues>`_.
In case of trouble, please check there if your issue has already been reported.
If you spotted it first, help us smashing it by providing a detailed and welcomed
`feedback <https://github.com/OCA/l10n-france/issues/new?body=module:%20l10n_fr_account_vat_return%0Aversion:%2014.0%0A%0A**Steps%20to%20reproduce**%0A-%20...%0A%0A**Current%20behavior**%0A%0A**Expected%20behavior**>`_.

Do not contact contributors directly about support or help with technical issues.

Credits
=======

Authors
~~~~~~~

* Akretion

Contributors
~~~~~~~~~~~~

* Alexis de Lattre <alexis.delattre@akretion.com>

Maintainers
~~~~~~~~~~~

This module is maintained by the OCA.

.. image:: https://odoo-community.org/logo.png
   :alt: Odoo Community Association
   :target: https://odoo-community.org

OCA, or the Odoo Community Association, is a nonprofit organization whose
mission is to support the collaborative development of Odoo features and
promote its widespread use.

.. |maintainer-alexis-via| image:: https://github.com/alexis-via.png?size=40px
    :target: https://github.com/alexis-via
    :alt: alexis-via

Current `maintainer <https://odoo-community.org/page/maintainer-role>`__:

|maintainer-alexis-via| 

This module is part of the `OCA/l10n-france <https://github.com/OCA/l10n-france/tree/14.0/l10n_fr_account_vat_return>`_ project on GitHub.

You are welcome to contribute. To learn how please visit https://odoo-community.org/page/Contribute.
