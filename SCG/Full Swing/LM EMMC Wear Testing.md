## Description
The LM had multiple hardware revisions, some of which looked into swapping out EMMC chips. During such swaps, it was crucial to ensure that the EMMC maintained integrity through a minimum number of read/write cycles. After fulfilling the minimum, the tests were continued to see how many cycles it would take to corrupt a given EMMC's storage.

## Take-Aways
* Start Date: 2023-03-02
* End Date: 2020-07-10
* Team Work Description: Sole developer
* Languages Used: bash/shell
* Tools/Frameworks Used: systemctl
* Platform: Embedded Linux

### Work Performed
- Created a system service based off of a binary found from this repo: https://github.com/ncw/stressdisk
- Reported read/write cycles performed before corruption occurred

### Accomplishments
- Learned how to build custom services using systemd (systemctl)
- Learned how EMMC wear testing is performed
