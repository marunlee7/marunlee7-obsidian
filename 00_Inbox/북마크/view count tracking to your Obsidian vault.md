---
aliases: []
title: view count tracking to your Obsidian vault
level: T02
file_role: article_atom
parent: "북마크"
word_type: t3전용 # T03 전용 필드 (빈 값 유지)
status: planned
priority: medium
process: raw
source_name: view count tracking to your Obsidian vault
source_author: "self"
source_type: "article"  
references: https://github.com/decaf-dev/obsidian-view-count?tab=readme-ov-file#sync-view-count-to-frontmatter
tags: [출처/외부_수집/북마크]
---
# View Count Tracking to Your Obsidian Vault

**[obsidian-view-count](https://github.com/decaf-dev/obsidian-view-count)** Public
generated from [obsidianmd/obsidian-sample-plugin](https://github.com/obsidianmd/obsidian-sample-plugin)
Add view count tracking to your Obsidian vault
[MIT license](https://github.com/decaf-dev/obsidian-view-count/blob/master/LICENSE)

[Open in github.dev](https://github.dev/) [Open in a new github.dev tab](https://github.dev/) [Open in codespace](https://github.com/codespaces/new/decaf-dev/obsidian-view-count?resume=1)

View count is an [Obsidian.md](https://obsidian.md/) plugin for desktop and mobile. It allows you to track the view count for each file in your vault.

- [Videos](https://github.com/decaf-dev/?tab=readme-ov-file#videos)
- [Installation](https://github.com/decaf-dev/?tab=readme-ov-file#installation)
- [Usage](https://github.com/decaf-dev/?tab=readme-ov-file#usage)
- [Dataview](https://github.com/decaf-dev/?tab=readme-ov-file#dataview)
- [API](https://github.com/decaf-dev/?tab=readme-ov-file#api)
- [Settings](https://github.com/decaf-dev/?tab=readme-ov-file#settings)
- [License](https://github.com/decaf-dev/?tab=readme-ov-file#license)

## Videos

Basic plugin usage

Screen.Recording.2024-06-28.at.4.15.20.PM.mov<video src="https://private-user-images.githubusercontent.com/40307803/344327942-e51fec6b-2549-4c3a-bff3-65f6d3009671.mov?jwt=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3NjAzOTMwNzMsIm5iZiI6MTc2MDM5Mjc3MywicGF0aCI6Ii80MDMwNzgwMy8zNDQzMjc5NDItZTUxZmVjNmItMjU0OS00YzNhLWJmZjMtNjVmNmQzMDA5NjcxLm1vdj9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNTEwMTMlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjUxMDEzVDIxNTkzM1omWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTAxNWI5ODlkYzk0MGJhZmEzNzVjNjZjM2QwZjk2ZDBjMWFmYzYyZGNhZjM3YTA1MDc1NWMwMDExZWE0NTI3YzMmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0In0.4vYdIJ3wYj6OlQulCD2mlFASi-1Mq_4acQdUMoAL6W0" controls="controls"></video>  

The [sync view count to frontmatter](https://github.com/decaf-dev/?tab=readme-ov-file#sync-view-count-to-frontmatter) setting

Screen.Recording.2024-06-28.at.4.24.16.PM.mov<video src="https://private-user-images.githubusercontent.com/40307803/344328938-2e245b7d-a4f6-4e39-b115-6f0de71e7cba.mov?jwt=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3NjAzOTMwNzMsIm5iZiI6MTc2MDM5Mjc3MywicGF0aCI6Ii80MDMwNzgwMy8zNDQzMjg5MzgtMmUyNDViN2QtYTRmNi00ZTM5LWIxMTUtNmYwZGU3MWU3Y2JhLm1vdj9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNTEwMTMlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjUxMDEzVDIxNTkzM1omWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPWM3OTc5Nzg1NzdiMGIwMjdiYjkzOGYzMTUzMDU4NzNlOTJiNzczYzJiZWY2YTIyZGFkOTJhNGY4MmU3N2I3NjYmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0In0.VYLEgBx7-B1n3IEdYOy-uOY1abWsFXq9YSK35RhVt6c" controls="controls"></video>  

The [view count type](https://github.com/decaf-dev/?tab=readme-ov-file#view-count-type) setting

Screen.Recording.2024-06-28.at.4.32.03.PM.mov<video src="https://private-user-images.githubusercontent.com/40307803/344330157-ba3a4317-5307-40db-8bbe-75d686ae0e4f.mov?jwt=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3NjAzOTMwNzMsIm5iZiI6MTc2MDM5Mjc3MywicGF0aCI6Ii80MDMwNzgwMy8zNDQzMzAxNTctYmEzYTQzMTctNTMwNy00MGRiLThiYmUtNzVkNjg2YWUwZTRmLm1vdj9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNTEwMTMlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjUxMDEzVDIxNTkzM1omWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPWNkYWQ4NmE0YjVmOTA4OWYxMjg0MjgxYmNhODEyYWQxODZiNmUzYTE3Y2VmYTlhZTI3YjNhNGYzZjIxOWI3YjQmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0In0.hXB6foqvOJMOLij4rC1rqDkCB6mNVN9cesjeZmLJicc" controls="controls"></video>

## Installation

1. In Obsidian, open **Settings**
2. Go to **Community plugins**
3. Select **Browse**
4. Search for **View Count** by **DecafDev**
5. Select **Install**
6. Then select **Enable**

## Usage

Once you enable the plugin, view count data will start being tracked. You can see the view count on desktop in the status bar in the bottom righthand corner.

There are 2 types of view count. [View count type](https://github.com/decaf-dev/?tab=readme-ov-file#view-count-type)

If you would like to view the view count on mobile, you will need to enable the [Sync view count to frontmatter](https://github.com/decaf-dev/?tab=readme-ov-file#sync-view-count-to-frontmatter) setting.

By default, the plugin will add a view to the sidebar called **View count**. You may access this view by opening the sidebar and clicking on the eye icon.

If the view is not open, you may run **Open view count view** from the command palette.

There are 2 different lists within the view count:

- A list of the most viewed notes in your vault sorted in descending order. Click on the eye icon to see this list.
- A list of the notes with the highest trending weight sorted in descending order. Click on the trending icon to see this list.

## Dataview

You may dynamically query view count data using the [Dataview plugin](https://obsidian.md/plugins?id=dataview)

If you have **Sync view count to frontmatter** enabled you may query the view count property from the frontmatter of each note.

```
\`\`\`dataview
TABLE view-count AS "View Count" SORT view-count DESC LIMIT 10
\`\`\`
```

Let's analyze this codeblock:

1. Render a table using the [Dataview Query Language](https://blacksmithgu.github.io/obsidian-dataview/queries/structure/)
2. Query the `view-count` property in each note
3. Display that property in a column called "View Count"
4. Sort the results in descending order (highest to lowest)
5. Limit the results to 10 notes

Let's analyze this codeblock:

1. Render a table using the [DataviewJS](https://blacksmithgu.github.io/obsidian-dataview/api/intro/)
2. Display 2 columns in the table: "Name" and "Trending Weight"
3. Query all markdown files
4. Sort the files based on the trending weight in descending order (highest to lowest)
5. Format an array of data that includes object with just the file name and the trending weight
6. Limit the results to 10 notes

The time period can be updated with various values. See the [time period](https://github.com/decaf-dev/?tab=readme-ov-file#time-period) section below.

## API

The view count plugin exposes an API that can be used to fetch the view count or trending weight for any file.

To start, you need to access the view count cache.

```
//Get the view count plugin
const plugin = this.app.plugins.plugins["view-count"];

//Get the view count cache
const cache = plugin.viewCountCache;
```

Then you can use the cache to get a view count or trending weight.

Here are the typescript definitions for these functions:

### Time Period

The `getTrendingWeight` function accepts a time period.

Here are the options:

| Value | Description |
| --- | --- |
| `3-days` | The last 3 days |
| `7-days` | The last 7 days |
| `14-days` | The last 14 days |
| `30-days` | The last 30 days |
| `today` | The start of the current day |
| `week` | The start of the week i.e. Sunday |
| `week-iso` | The start of the iso week i.e. Monday |
| `month` | The start of the month e.g. January 1 |

## Settings

### Count Method

The method used to calculate view counts. This can be the total number of times a file has been opened or the unique days a file has been opened.

For example, consider a user that opened a file 3 times in 1 day. Using `Total times opened` the view count would be 3. However, using `Unique days opened` the view count would be 1.

A unique day is considered an opening of a file after 12 am local time.

### Excluded Paths

The folder paths that should be excluded from view count tracking. Please separate individual paths by commas e.g. `folder1,folder2`

The view count for all files is stored in a JSON file located in the Obsidian configuration folder e.g. `.obsidian/view-count.json`. When `Sync view count` is enabled, the plugin will add a view count property to all notes and continuously update them to match the values stored in the JSON file.

Enabling this setting makes view count visible on mobile devices.

When enabled, new notes will not have a view count property added upon creation. However, if `Sync View Count` is enabled, a property will be added when the note is opened.

### Property name

The name of the property that the view count will be stored in.

### Templater Delay

The time to wait in milliseconds before adding a view count property to a new note. You should increase this value if you're using the [Templater plugin](https://github.com/SilentVoid13/Templater) and the template applied during new note creation is being overwritten.

## License

View Count is distributed under [MIT License](https://github.com/decaf-dev/obsidian-view-count/blob/master/LICENSE)

## Releases 33

[\+ 32 releases](https://github.com/decaf-dev/obsidian-view-count/releases)

## Sponsor This Project

- [https://ko-fi.com/decaf\_dev](https://ko-fi.com/decaf_dev)
