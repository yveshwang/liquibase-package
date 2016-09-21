Title: README.md
Author: Yves Hwang
Email: yveshwang at gmail dot com
Date: 21.09.2016

# liquibase-package

## luquibase
RDMS refactoring tool. Binaries and spec filed are pulled down from their releases, and slightly edited.

Go into liquibase/ folder. To build the rpm, you want to do the following:

    cd liquibase/
    rm -rf rpm-build/
    sudo yum check-update
    sudo yum install rpm-build
    sudo yum install redhat-rpm-config
    mkdir -p rpm-build/
    wget https://github.com/liquibase/liquibase/releases/download/liquibase-parent-3.5.1/liquibase-3.5.1-bin.tar.gz
    mkdir -p liquibase-3.5.1/
    tar xvf liquibase-3.5.1-bin.tar.gz -C liquibase-3.5.1/
    tar cvzf liquibase-3.5.1.tar.gz liquibase-3.5.1/
    cp liquibase-3.5.1.tar.gz rpm-build/SOURCES/.
    rpmbuild --define "_topdir %(pwd)/rpm-build" -bb liquibase.spec
