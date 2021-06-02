---
## Common
title: Post Template
tags: [tag1, tag2]
description: 
published: true

## Github pages
layout: post
# image: 
sitemap: false
hide_last_modified: false
no_break_layout: false


## Dev.to
# cover_image: 
# canonical_url: 
# series:

---

# Draft GraphQL backend — authorization & authentication

## Background

In any system where users interacting with each other, authorization & authentication are the main key elements that controls what each user can do. With this in mind, I present PoriJobs — a graphql backed job portal. Overview of roles and permissions are simple here.

| Roles     | Permissions                              | Remarks                                                                              |
| --------- | ---------------------------------------- | ------------------------------------------------------------------------------------ |
| Visitor   | View jobs                                | A casual surfing user, can go through jobs. To apply he'll need an applicant account |
| Applicant | View/Apply to job                        | Applicant who can surf and apply jobs                                                |
| Employer  | Post/View job, Update status[open/close]; View applicants | Company that posts jobs                                                              |
| Admin     | Overall user management                  | System admin                                                                         |

## Resources

Let's quickly go through the resources that exposed to users. This will help us understand how it works.

**Job** — A job is created by *Employer* targetting *Applicants*. This resource can be in *Open* state to receive applications or *Close*d to disappear from listing.

**Application** — Job application is created by *Applicant/Employee* to show interest in a job. This will be 