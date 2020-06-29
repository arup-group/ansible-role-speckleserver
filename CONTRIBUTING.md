Contributing to this project
============================

## You should:

* Run ansible-lint over any changes you make. If you have pre-commit (pre-commit.com) installed on your system, then the pre-commit hook will do this for you.

* If you have the molecule test framework installed and an appropriate docker daemon set up, giving it a test run via `molecule test` is a good idea. check the README for instructions, and test against all supported distributions.

* I prefer to take pull requests over direct checkins, just so I can review any changes for sanity / coding style. Bad checkins and bodgy pull requests will be reverted/rejected.

* Keep the ansible version requirements sensible. the last two releases is fine, do not go overboard supporting ancient versions of Ansible, users can upgrade their copies easily.

## However you should not:

* Add un-necessary dependencies. If you need extra libraries or additional tasks for a given environment, add pre_task/post_task plays in your site playbook. I have spoken.

* **This is a distribution-agnostic package** do not add any tasks or additions that favour/enhance/work for one specific distribution. Changes work on either all distributions or none of them. I have spoken.

* The defaults are intended to be sensible and workable for all practical scenarios. They are easily overridden in playbook-hosted vars, or group_vars/host_vars files in your working directory. Do not change defaults or vars in the role directly unless you know what you are doing and have a good reason to do so. I have spoken.

* Run tests with versions later than 2.22, you will fall down a rabbit hole you really want to avoid. `pip install --user molecule==2.22` is your friend. 3.0.x is broken right now. I have spoken (from firsthand experience)

* The maintainer reserves the right to revert any breakage caused by not following the above points. I have spoken.
