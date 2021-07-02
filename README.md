<p align="center">
  <img src="images/credible.svg" width="350">
</p>

# Assignment
+ You're at a company that is "shifting left" and trying to implement Docker Image scanning as a part of the code review process. In particular, when an Engineer submits a Pull Request, all Dockerfiles (within the repo) need to be scanned for vulnerabilities.

# Initialization
+ `git clone https://github.com/zroof-credible/appsec-assignment.git`
    + During the assignment, you will be adding files to this repo (in your own environment).
    + **HINT:** You should transfer this repository to a private repo (in your own Github account).  This will allow you to test the Github Actions integration that you will create (more context below).

# Main Logic
1. Create a Python script that:
    + Iterates through all "Docker applications" in the `docker` directory (e.g., `docker/app1`, `docker/app2`, `docker/app3`).
    + For every "Docker application", build the corresponding Docker Image and run [Trivy](https://github.com/aquasecurity/trivy) on the built image.
    + For every [Trivy](https://github.com/aquasecurity/trivy) scan, log the results to stdout.
        + **HINT:** Think about the developer experience.
    + If a `HIGH` or `CRITICAL` vulnerability is found, exit with a non-zero status code.
        + **NOTE:** You must scan all "Docker applications" before you emit the status code.  In other words, you can't fail the script on the first `HIGH` or `CRITICAL` vulnerability.

2. Use [Github Actions](https://docs.github.com/en/actions) to:
    1. Run the Python script whenever a Pull Request occurs.

# Extra Credit
1. Each of the Dockerfiles has an explicitly defined vulnerability.  However, in one case, Trivy doesn't find a vulnerability.  Why did this occur?
    + **HINT:** You shouldn't need more than 1 paragraph to answer this.
2. Within the Pull Request process, how could you automatically "block" `HIGH` or `CRITICAL` vulnerabilities from being merged?
    + **HINT:** You shouldn't need more than 1 paragraph to answer this.


# Tips
+ Wherever possible, use best practice Software Development principles (e.g., exception handling, classes, etc.)
+ While it's encouraged to leverage preexisting libraries, please do not *blindly* copy preexisting work.  During the in-person interview, you will be asked questions on your submission (including why you made certain decisions, etc.)
+ This probably goes without saying, but please do NOT publicly share the contents of this repo.
+ Do not stress :smile:  Given the time constraint, we realize this isn't going to be perfect.

# Help
+ If you have **technical** questions, please email Zach Roof (zroof@credible.com)
+ If you have **non-technical** questions (i.e., extending the amount of time needed, etc.), please email Magda (mmaldonado@credible.com).

# Submission
+ After receiving the assignment, you have 1 week to finish.
+ Please submit the assignment (as a `.zip`) to Madga.  If you did the extra credit, create a `extra-credit.txt` (within the `.zip`).
    + **NOTE**: We're already on the lookout for [zip bombs](https://en.wikipedia.org/wiki/Zip_bomb), so don't even try :wink:
