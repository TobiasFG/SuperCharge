# How to persist questions and answers related to the codebase

The provided questions and answers may not be optimally written. Remove fluff without removing important content, then persist cleaned findings to target path in this format:

```
# High-level codebase information

## Purpose

[Answer]

## Programming languages

[Answer]

## Tooling

[Answer]

...

```

## Example of provided provided questions and answers

```
Question: What is the high-level purpose of the codebase?
Answer: This codebase has been developed for a customer to handle their pricing logic for their ecommerce solutions, such as their webshop. It is very complicated and very important to ensure works correctly.

Question: What programming languages are used?
Answer: We use primarly C#, but there is also some javascript, html, and css for the frontend.

Question: What specific tooling are used?
Answer: We primarly use visual studio code and microsoft's sql server studio. We also have some scripts to generate a few boiler plate files when needed. Oh and we also use Bruno for endpoint testing and Swagger for documentation.

Question: What specific frameworks & packages are used?
Answer: We use many frameworks, but most are npm packages for the frontend, not sure which are used completely and for what. For C# development we use dapr and EF.

Question: What cloud provider or hosting is used?
Answer: We use Microsoft azure as our cloud and hosting provider.

...

Question: Any other important notes?
Answer: It is really important that we do not write bad code that can break stuff. We also have a policy that we do not introduce new packages unless approved by the lead architect. And also remember that we are targeting dotnet 10.

```

## Example of good persisted result

```
# High-level codebase information

## Purpose

Business critical pricing component for ecommerce solutions.

## Programming languages

- C#
- Javascript
- HTML
- CSS

## Tooling

- Visual Studio Code 
- SQL Server Management Studio (SSMS)
- Bruno
- Swagger

## Frameworks & Packages?

- Dapr
- Entity Framework
- Assortment of NPM packages for frontend.

## Cloud provider & Hosting 

Microsoft Azure

...

## Important notes

- New packages may not be installed unless approved by the lead architect. 
- Solution is targeting DotNet 10.

```

## Rules

- Keep exact answers where they are already clear.
- Normalize grammar, not meaning.
- Preserve unknowns as `Unknown`.
- Keep sections short and direct.
