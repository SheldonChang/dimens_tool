# dimens_tool

Be sure  that the base file contains all values you need.

modify ${support_dp_arr}

usage: ./dimen_gen.sh values-sw{base}dp/dimens.xml 

+++++++++++++++++++++++++++++++++++++++++++++++++++++++++

Gardle Usage:
add to app/build.gradle

task dimensionPrebuildTask(type: Exec) {

    executable 'bash'
    workingDir "$projectDir"
    args '-c', './dimen_gen.sh ./src/main/res/values-sw600dp/dimens.xml'
    ignoreExitValue true
}

build.dependsOn preBuild
preBuild.dependsOn dimensionPrebuildTask

