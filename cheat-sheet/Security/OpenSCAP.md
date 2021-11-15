## CLI

Get ruleset infos

    oscap info /usr/share/xml/scap/ssg/content/ssg-rhel7-ds.xml
    oscap info /usr/share/xml/scap/ssg/content/ssg-centos7-ds.xml

Evaluation example

    oscap xccdf eval --report report.html --profile xccdf_org.ssgproject.content_profile_pci-dss /usr/share/xml/scap/ssg/content/ssg-rhel7-ds.xml

Evaluate and remediate

    oscap xccdf eval --remediate --profile xccdf_org.ssgproject.content_profile_rht-ccp --results scan-xccdf-results.xml /usr/share/xml/scap/ssg/content/ssg-rhel6-ds.xml

Generate remediation shell script for review

    oscap xccdf generate fix --template urn:xccdf:fix:script:sh --profile xccdf_org.ssgproject.content_profile_rht-ccp --output my-remediation-script.sh /usr/share/xml/scap/ssg/content/ssg-rhel6-ds.xml
    
## Install

    apt-get install ssg-debderived     # Ubuntu
    apt-get install ssg-debian         # Debian
    yum install scap-security-guide    # Fedora/Redhat

## Misc

- [OpenSCAP on Ubuntu](https://www.techrepublic.com/article/how-to-perform-security-audits-on-ubuntu-server-with-openscap/)
- [Compliance as Code](https://github.com/ComplianceAsCode/content)