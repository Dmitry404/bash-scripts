#!/bin/bash

GLOBAL_JAVA_VERSION=${1:-"1.8"}

function rebuild() {
    echo "removing jenv links"
    rm -r ~/.jenv/versions/*

    echo "adding existing JVMs"
    for i in $( ls /Library/Java/JavaVirtualMachines/ ); do
        jenv add "/Library/Java/JavaVirtualMachines/$i/Contents/Home"
    done

    echo "setting default java version to $GLOBAL_JAVA_VERSION"
    jenv global $GLOBAL_JAVA_VERSION
}

while true; do
    read -p "You are going to re-build jenv links. Sure enough?`echo $'\n> '`" answer
    case $answer in
        [Yy]* ) rebuild; break;;
        [Nn]* ) exit;;
        * ) echo "Please type yes or no.";;
    esac
done

