# dimens_tool

Be sure  that the base file contains all values you need.

modify ${support_dp_arr}

usage: ./dimen_gen.sh values-sw{base}dp/dimens.xml 

+++++++++++++++++++++++++++++++++++++++++++++++++++++++++

Gardle Usage:
add below to app/build.gradle

task dimensionPrebuildTask(type: Exec) {

    executable 'bash'
    workingDir "$projectDir"
    args '-c', './dimen_gen.sh ./src/main/res/values-sw600dp/dimens.xml'
    ignoreExitValue true
}

preBuild.dependsOn dimensionPrebuildTask

+++++++++++++++++++++++++++++++++++++++++++++++++++++++++

How to know smallest width (sw) of an android device?

Configuration config = getResources().getConfiguration();  
config.smallestScreenWidthDp

https://android-developers.googleblog.com/2011/07/new-tools-for-managing-screen-sizes.html
