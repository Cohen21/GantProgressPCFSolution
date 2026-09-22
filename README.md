# GantProgressPCFSolution

A PowerApps Component Framework (PCF) control for Microsoft Dynamics 365 / Power Platform, rendering employee tasks as an interactive **Gantt-style progress timeline**.

## Overview

This control visualizes tasks assigned to employees on a horizontal timeline, showing progress, duration, and status at a glance — directly embedded on a model-driven app form or view, without leaving Dynamics 365.

## Features

- Timeline view of tasks per employee, grouped and sorted by date
- Visual progress indication per task (e.g. percentage complete, status color-coding)
- Responsive layout for different form/section sizes
- Built with TypeScript and the PCF framework, deployable to any Dataverse environment

## Prerequisites

- [Power Platform CLI (`pac`)](https://learn.microsoft.com/power-platform/developer/cli/introduction)
- Node.js (LTS version)
- Access to a Dataverse environment with System Customizer (or higher) privileges

## Project Structure
cat > README.md << 'EOF'
# GantProgressPCFSolution

A Power Platform Solution containing a PCF (PowerApps Component Framework) control for Microsoft Dynamics 365, rendering employee tasks as an interactive **Gantt-style progress timeline**.

## Overview

This control visualizes tasks assigned to employees on a horizontal timeline, showing progress, duration, and status at a glance — directly embedded on a model-driven app form or view.

## Features

- Timeline view of tasks per employee, grouped and sorted by date
- Visual progress indication per task (percentage complete, status color-coding)
- Responsive layout for different form/section sizes
- Packaged as a Dataverse Solution for straightforward import into any environment

## Project Structure

GantProgressPCFSolution/
- GantPCF/                  PCF control source (TypeScript, manifest, CSS)
- Other/                    Solution.xml, Customizations.xml (solution metadata)
- bin/                      Build output (ignored — not tracked in Git)
- GantProgressPCFSolution.cdsproj

## Prerequisites

- Power Platform CLI (pac)
- .NET SDK (msbuild)
- Node.js (LTS version)

## Build

msbuild /t:build /restore

This produces the packaged solution .zip under bin/Debug/ (or bin/Release/ for a managed build).

## Deploy to a Dataverse environment

1. pac auth create --url https://<yourorg>.crm4.dynamics.com
2. Import the generated .zip via the Power Platform Admin Center, or:
   pac solution import --path bin/Debug/GantProgressPCFSolution.zip

## Local PCF Testing (before packaging)

cd GantPCF
npm install
npm start watch

## Adding the control to a form

1. Open the target table's form in the form editor.
2. Select/add the bound field.
3. Components → Get more components → select the Gantt control.
4. Save and publish.

## Data Binding

To be documented: exact fields/entities expected (task start date, end date, percent complete, employee lookup).

## Release Downloads

Packaged solution .zip files for tagged versions are available under the repository's **Releases** tab, rather than tracked directly in source control.

## License

Internal / Proprietary — QMatrix GmbH.
EOF

git add README.md
git commit -m "Add README"
git push
