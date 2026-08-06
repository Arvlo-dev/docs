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
<Tabs>
  <Tab label="Preview">

<Callout title="Info" type="info">
This is the style applied if the card type is set to "info" or "note." This is also applied if no type is specified.
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

  </Tab>

  <Tab label="Code">

```mdx
<Callout title="Info" type="info">
  This is the style applied if the card type is set to "info" or "note."
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
```

  </Tab>
</Tabs>

## Card Grid
<Tabs>
  <Tab label="Preview">

<CardGrid cards={cards} />

  </Tab>

  <Tab label="Code">

```mdx
<CardGrid cards={cards} />
```

  </Tab>
</Tabs>

## Tabs
<Tabs>
  <Tab label="Preview">

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

  </Tab>

  <Tab label="Code">

````mdx
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
`````

  </Tab>
</Tabs>


## File Tree

<Tabs>
  <Tab label="Preview">

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

  </Tab>

  <Tab label="Code">

```mdx
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
```

  </Tab>
</Tabs>


## Steps

<Tabs>
  <Tab label="Preview">

<Steps>
  <Step title="Install the package">
    Run the install command.
  </Step>

  <Step title="Configure your environment">
    Add your API key.
  </Step>
</Steps>

  </Tab>

  <Tab label="Code">

```mdx
<Steps>
  <Step title="Install the package">
    Run the install command.
  </Step>

  <Step title="Configure your environment">
    Add your API key.
  </Step>
</Steps>
```

  </Tab>
</Tabs>

## Do's and Don'ts
<Tabs>
  <Tab label="Preview">

<DoDont>
  <Do>
    Store secrets in environment variables.
  </Do>

  <Dont>
    Commit API keys to your repository.
  </Dont>
</DoDont>

  </Tab>

  <Tab label="Code">

```mdx
<DoDont>
  <Do>
    Store secrets in environment variables.
  </Do>

  <Dont>
    Commit API keys to your repository.
  </Dont>
</DoDont>
```

  </Tab>
</Tabs>

## API Block
<Tabs>
  <Tab label="Preview">

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

```json
{
  "title": "Building fire",
  "priority": "high"
}
```

</ApiBlock>

  </Tab>

  <Tab label="Code">

````mdx
<ApiBlock
  method="POST"
  path="/api/incidents"
  description="Create a new incident."
  params={[ ... ]}
  responses={[ ... ]}
>

```json
{
  "title": "Building fire",
  "priority": "high"
}
```

</ApiBlock>
````

  </Tab>
</Tabs>

## Recipe
<Tabs>
  <Tab label="Preview">

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

  </Tab>

  <Tab label="Code">

```mdx
<Recipe
  title="Upload a file to S3"
  description="This guide walks you through uploading a file using the SDK."
>
  ...
</Recipe>
```

  </Tab>
</Tabs>

## Tooltip
<Tabs>
  <Tab label="Preview">

A <Tooltip text="A unique identifier for a record.">UUID</Tooltip> is generated automatically.

  </Tab>

  <Tab label="Code">

```mdx
A <Tooltip text="A unique identifier for a record.">UUID</Tooltip> is generated automatically.
```

  </Tab>
</Tabs>

## Version Badge
<Tabs>
  <Tab label="Preview">

<VersionBadge version="v2.1+" />

  </Tab>

  <Tab label="Code">

```mdx
<VersionBadge version="v2.1+" />
```

  </Tab>
</Tabs>

## Status Badge
<Tabs>
  <Tab label="Preview">

<Status type="beta" />
<Status type="deprecated" label="Removed soon" />

  </Tab>

  <Tab label="Code">

```mdx
<Status type="beta" />
<Status type="deprecated" label="Removed soon" />
```

  </Tab>
</Tabs>

## Doc Card
<Tabs>
  <Tab label="Preview">

<DocCard
eyebrow="Next guide"
title="Configure dispatch workflows"
description="Set up routing rules, roles, and notification behavior."
href="/docs/ready911/workflows"
/>

  </Tab>

  <Tab label="Code">

```mdx
<DocCard
  eyebrow="Next guide"
  title="Configure dispatch workflows"
  description="Set up routing rules, roles, and notification behavior."
  href="/docs/ready911/workflows"
/>
```

  </Tab>
</Tabs>
