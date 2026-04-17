---
type: assignment
date: 2026-04-17T0800-0400
title: "Project 4 -- Image Generation"
jupyter: /static_files/assignments/project4.ipynb
colab: https://colab.research.google.com/github/DL4DS/sp2026/blob/main/static_files/assignments/project4.ipynb
hide_from_announcements: false
published: true
due_event:
    type: due
    date: 2026-04-30T23:59:00-5:00
    description: 'Project 4 due'
---

**Project 4 -- Image Generation**

Your task for this project is to build a generative model for cute animal
pictures based on a provided data set. You may use any of the generative
modeling types discussed in class so far (GANs, VAEs, and diffusion models),
but you are encouraged to try and implement diffusion models.

Because the data set you are using is already copied to SCC, you may want to
copy the notebook to your SCC directory and run it there. The easiest way to do
that is to run the following commands:

```bash
cd /projectnb/dl4ds/students/YOUR-USERNAME
mkdir project4
cd project4
wget https://raw.githubusercontent.com/DL4DS/sp2026/refs/heads/main/static_files/assignments/project4.ipynb
```

**Do not copy the data set to your SCC directory!!**

Then you can create a new interactive Jupyter notebook session from the SCC
OnDemand dashboard with the following suggested settings:

- **List of modules to load:** `miniconda academic-ml`
- **Pre-launch command:** `conda activate spring-2026-pyt`
- **Interface:** `lab`
- **Working directory:** `/projectnb/dl4ds/students/YOUR-USERNAME`
- **Number of CPUs:** `4`
- **Number of GPUs:** `1`
- **GPU compute capability:** `7.0`
- **Project:** `dl4ds`

> Note: You can try a lower GPU compute capability than 7.0 and in
> fact you will get a GPU compute node more quickly, but it seems
> that the `academic-ml` module requires GPUs of at least version 7.0.

Turn in on Gradescope.

Have fun!
