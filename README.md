[![CIF dictionary check](https://github.com/COMCIFS/MultiBlock_Dictionary/actions/workflows/main.yml/badge.svg)](https://github.com/COMCIFS/MultiBlock_Dictionary/actions)

# MultiBlock_Dictionary

Definitions describing data stored in multiple containers

# When to use this dictionary

Use this dictionary if you need to store related data in more than one
data container (e.g. multiple CIF data blocks and/or multiple files).

# Technical background

## Introduction

Data names defined in CIF dictionaries belong either to `Loop` or `Set`
categories. Data names belonging to `Loop` categories may take multiple
values in a CIF data block by being placed in a `loop` together with
other data names from that category. Data names in `Set` categories,
by contrast, may only take a single value in a single data block.

The core CIF dictionary restricts various data names to being single-valued
in a single data block by assigning them to `Set` categories. For example,
as defined in the CIF core dictionary, a single data block may
only contain one set of diffraction conditions (one temperature, one
pressure) and describe data from one crystal. In order for more complex
experiments to be described, data can be distributed over multiple data
blocks. The multiblock dictionary provides category and data name definitions
to enable such multi-block data sets to be correctly combined.

## Changes to CIF core category definitions

`Set` categories must have at least one `_category_key.name`
attribute defined in order for data items from those categories to
be properly defined and referred to. The various child data names
of those new key data names should also be added.

This dictionary redefines Set categories to include the new
    key data names, adds the key data name definitions, and defines
    any linked and child data names.
