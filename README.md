# Personal Portfolio Assignment

# Updated Page

I have put together a better version of this [on my GitHub](https://github.com/userbradley/portfolio-project) that you are free to follow!

---

## Aims of this

This assignment is set out to act as a little project that you need to manage and keep on track. Think of this as you first cloud deployment from a client.

## What you'll need to do:

Like mentioned above, you are to treat this as a client project, so you **need** to keep the shareholders up to date on progress and issues you're facing. Ensure that clarifying questions are asked as early on as possible to avoid delay.

## The assignment:

### Description

Build and deploy a personal portfolio that showcases:
* Previous work experiences
* Projects of note
* Certifications
* About you professionally (Professional Blurb)
* About you personally (Personal blurb, eg: I enjoy fishing, I race cars etc)

### Tech stack you **must** use:

* Docker 
    * You need to build the site as a docker image
* Cloud Run 
* Terraform
* Git

### Acceptance criteria

* Site is built using something like [mkdocs](https://www.mkdocs.org) or [hugo](gohugo.io/) - A static site.
* The site is then built as a docker container
* Docker container is pushed to [gcr.io](https://cloud.google.com/container-registry/)
* Security scan is run using something like [trivy](https://aquasecurity.github.io/trivy/) - The less CVE's the better! 
* Keep a decision log! I want to know why you've done things the way you have!


### Extra points to earn!

Build a CICD pipeline around the site to automatically deploy it to Cloud Run once a change is made!

### How to present:
* **Fork this repo** (Click fork at the top right)
* Rename this file to `og.README.md`
* Make your own `README.md` files where ever you feel needed
* Make a `decisions.md` file
* Link me to the finished code!


#### decisions.md

This file should be created each time you've made a decision.

Try and number it! 

Let's say you've decided not to use mkdocs and use hugo, so your document would look like:
```markdown
# Deision Log

## 1: Hugo over mkdocs

### Reason:

I found that the pre-built templates are better and easier to edit, as well as the build process etc...
```

Where you're making decisions in code, eg: Not using a module, do the below:

`lb.tf`
```terraform
resource "google_compute_url_map" "default" {
  name            = "bysd-portfolio-urlmap"
  default_service = google_compute_backend_service.default.id
}
# Decision #2
```

`decisions.md`
```markdown
# Deision Log

## 2: Building my own code over the terraform module

### Reason:

I wanted to learn how to build a full Load balancer with NEG so used my own code over the module.
```

## Closing notes:

Ask questions, this isnt a "Here's your assignment, go", it's a learning opportunity.

## Example code: 

Without giving away too much, mkdocs config files are strange if you've never used it before:

[mkdocs example](https://gist.github.com/userbradley/9aabac20e47c420e07b9bc0621378310)

## Example site:

[bradley.breadnet.co.uk](https://bradley.breadnet.co.uk)
