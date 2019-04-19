# 테스팅

## Automated testing

Run `pxt checkdocs --snippets` in the project's root directory. This will automatically check both the validity of referring links in your docs and that all code snippets in your documentation can be compiled. It checks to see that no typescript features that can't be represented as blocks are used in any block snippets.

If you use additional dependencies, make sure you reference them (see [Anchors](/writing-docs/anchors#dependencies)).

To exclude a snippet from being checked, add `-ignore` after the snippet type (see [Macros](/writing-docs/macros#ignore)).