# AllUnits — Fuuz Units of Measure Package

> **Beta concept — not an accelerator.** Published as a working concept to read, run
> and take the pattern from. It is not a supported deliverable, it carries no service
> level agreement, and it may change or be withdrawn without notice.

A comprehensive Fuuz package containing all standard units of measure, unit types, and unit conversions for the Fuuz platform.

## Description

`AllUnits@2.0.0.fuuz` is a Fuuz platform package that provides a complete set of units of measure for use in any Fuuz application. It seeds three core data models — **UnitType**, **Unit**, and **UnitConversion** — giving your application a ready-to-use measurement system out of the box.

## Package Contents

| Data Model | Record Count | Description |
|---|---|---|
| **UnitType** | 30 | Categories that group related units (SI and Imperial variants) |
| **Unit** | 164 | Individual units of measure across all unit types |
| **UnitConversion** | 1,720 | Conversion factors between units within the same type |

### Unit Types Included

| Category | SI | Imperial |
|---|---|---|
| Area | Area (SI) | Area (Imperial) |
| Density | Density (SI) | Density (Imperial) |
| Energy | Energy (SI) | Energy (Imperial) |
| Flow Rate | Flow Rate (SI) | Flow Rate (Imperial) |
| Force | Force (SI) | Force (Imperial) |
| Length | Length (SI) | Length (Imperial) |
| Power | Power (SI) | Power (Imperial) |
| Pressure | Pressure (SI) | Pressure (Imperial) |
| Speed | Speed (SI) | Speed (Imperial) |
| Temperature | Temperature (SI) | Temperature (Imperial) |
| Torque | Torque (SI) | Torque (Imperial) |
| Volume | Volume (SI) | Volume (Imperial) |
| Weight | Weight (SI) | Weight (Imperial) |
| **Standalone** | | |
| Amount | — | — |
| Currency | — | — |
| Frequency | — | — |
| Time | — | — |

## When to Use This Package

Use this package when:

- You are setting up a **new Fuuz application** that requires a standardized set of units of measure.
- You need a **complete library** of SI and Imperial units with pre-built conversion factors.
- You want to **replace the platform's default seed data** with a more comprehensive unit system.

## How to Import

1. Download the `AllUnits@2.0.0.fuuz` file from this repository.
2. Open your Fuuz application in the platform.
3. **Drag and drop** the `.fuuz` file into the platform UI to import the package.

## Before You Import — Deleting Existing Seed Data

The Fuuz platform seeds default UnitConversion, Unit, and UnitType records into new applications. These **will conflict** with the package import. You must delete the existing seed data first by running the GraphQL mutations provided in [`deleteSeededUnitData.graphql`](deleteSeededUnitData.graphql).

**Mutations must be run in this order** (foreign key dependencies):

1. **`deleteUnitConversion`** — Remove seeded unit conversions first (they reference Units).
2. **`deleteUnit`** — Remove seeded units next (they reference UnitTypes).
3. **`deleteUnitType`** — Remove seeded unit types last.

The `deleteSeededUnitData.graphql` file contains all three mutations pre-built with the default seeded record IDs.

> **Note:** You may need to update the IDs in the mutations or add additional entries depending on your environment. If your application has had units modified, added, or removed since initial setup, the seeded record IDs may differ from the defaults provided.

## Package Metadata

| Field | Value |
|---|---|
| Package Name | `AllUnits` |
| Version | `2.0.0` |
| Spec Version | `2.0.0` |
| Platform Version | `2026.2.1.782` |
| Publisher | `fuuz` |

## Service levels

No service level agreement applies to anything published here. It becomes a supported
deliverable only once it has been implemented by a Fuuz services professional or an
approved Fuuz partner.
