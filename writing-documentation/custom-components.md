---
title: Custom Components
description: This page demonstrates all custom components provided by Arvlo.
---

export const cards = [
    {
        title: "Text Card",
        description: "Card with a fancy description."
    },
    {
        title: "Link Card",
        description: "Card with a fancy link.",
        href: "https://google.com"
    }
];

## Callout
<Callout title="Info" type="info">
    This is the style applied if the card type is set to "info" or "note." This is also applied if no type is specified in the opening tag.
</Callout>

<Callout title="Warning" type="warning">
    This is the style applied if the card type is set to "warning."
</Callout>

<Callout title="Danger" type="danger">
    This is the style applied if the card type is set to "danger."
</Callout>

<Callout title="Success" type="success">
    This is the style applied if the card type is set to "success."
</Callout>

## Card Grid
<CardGrid cards={cards} />

## Tabs
<Tabs>
    <Tab label="npm">
        ```bash
        npm install astro
        ```
    </Tab>

    <Tab label="pnpm">
        ```bash
        pnpm add astro
        ```
    </Tab>
</Tabs>

## File Tree
<FileTree
    items={[
        {
            name: "src",
            type: "folder",
            children: [
                {
                    name: "components",
                    type: "folder",
                    children: [
                        { name: "Callout.astro" },
                        { name: "CardGrid.astro" },
                        { name: "Tabs.astro" },
                        { name: "FileTree.astro" },
                    ],
                },
                { name: "pages", type: "folder" },
            ],
        },
        { name: "astro.config.mjs" },
    ]}
/>

## Steps
<Steps>
  <Step title="Install the package">
    Run the install command.
  </Step>

  <Step title="Configure your environment">
    Add your API key.
  </Step>
</Steps>

## Do's and Dont's
<DoDont>
  <Do>
    Store secrets in environment variables.
  </Do>

  <Dont>
    Commit API keys to your repository.
  </Dont>
</DoDont>

## API Block
<ApiBlock
  method="POST"
  path="/api/incidents"
  description="Create a new incident."
  params={[
    {
      name: "title",
      type: "string",
      required: true,
      description: "The incident title.",
    },
    {
      name: "priority",
      type: "low | medium | high",
      description: "The incident priority.",
    },
  ]}
  responses={[
    {
      status: 201,
      description: "Incident created.",
    },
    {
      status: 400,
      description: "Invalid request body.",
    },
  ]}
>
<br />
```json
{
  "title": "Building fire",
  "priority": "high"
}
```
</ApiBlock>

## Recipe
<Recipe
  title="Upload a file to S3"
  description="This guide walks you through uploading a file using the SDK."
>

  <RecipeStep title="Install the SDK">
    ```bash
    npm install @aws-sdk/client-s3
    ```
  </RecipeStep>

  <RecipeStep title="Initialize the client">
    ```ts
    const client = new S3Client({ region: "us-east-1" });
    ```
  </RecipeStep>

  <RecipeStep title="Upload the file">
    ```ts
    await client.send(new PutObjectCommand({
      Bucket: "my-bucket",
      Key: "file.txt",
      Body: file
    }));
    ```
  </RecipeStep>

  <RecipeResult>
    Your file is now available in S3.
  </RecipeResult>

</Recipe>

## Tooltip
A <Tooltip text="A unique identifier for a record.">UUID</Tooltip> is generated automatically.

## Version Badge
<VersionBadge version="v2.1+" />

## Status Badge
<Status type="beta" />
<Status type="deprecated" label="Removed soon" />

## Doc Card
<DocCard
  eyebrow="Next guide"
  title="Configure dispatch workflows"
  description="Set up routing rules, roles, and notification behavior."
  href="/docs/ready911/workflows"
/>