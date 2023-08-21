# Chapter 8 - Testing Strategies

Here is the purpose of each type of test and a very rough guideline for how much coverage we should aim for with them:

## Unit Tests - 90-100%

Tests written by programmers, for programmers that are for specifying the system at the lowest level and executed as part of Continuous Integration.

## Component Tests - 50%

Tests written by QA and Business with assistance from developers that should cover mostly happy-path and obvious corner cases to test that outputs from given inputs match expectations.

## Integration Tests - 20%

Tests typically written by system architects or lead designers to ensure that components are properly connected and communicate clearly with each other.

## System Tests - 10%

Tests typically written by system architects and technical leads that test correct system construction.

## Manual Exploratory Tests - 5%

Tests where testers, (or anyone really) seek to identify how well the system behaves under human operation and to creatively find as many ‘peculiarities’ as possible.
