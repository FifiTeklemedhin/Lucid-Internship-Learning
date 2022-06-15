# Things learned from my first commit

## Starting up 🎬
* only make changes to the component that the specific line of my task references (lol I totally spaced this one)
* need to run the server using [Instruction 5 of Simeon's startup guide](https://id.atlassian.com/login/authorize?application=confluence&continue=https%3A%2F%2Flucidatlassian.atlassian.net%2Flogin%3FredirectCount%3D1%26dest-url%3D%252Fwiki%252Fspaces%252FSIM%252Fpages%252F52616332350%252FCelica%252BMan%252Bs%252Bversion%252Bof%252Bfront-end%252Bdev%252Bsetup%26application%3Dconfluence&token=eyJraWQiOiJtaWNyb3NcL3NpZ24taW4tc2VydmljZVwvYXZqYjBxMmdhb3NzMThlbyIsImFsZyI6IlJTMjU2In0.eyJtYXJrZWRWZXJpZmllZCI6ImZhbHNlIiwibG9naW5UeXBlIjoic2Vzc2lvblJlZnJlc2giLCJpc3MiOiJtaWNyb3NcL3NpZ24taW4tc2VydmljZSIsInVzZXJJZCI6IjViYWVhYzQxYzJkZTA3NjZhZDIxNzhlOCIsImlzU2xhY2tBcHBTb3VyY2UiOiJmYWxzZSIsImF1ZCI6Imxpbmstc2lnbmF0dXJlLXZhbGlkYXRvciIsIm5iZiI6MTY1NTMwODg2Nywic2NvcGUiOiJMb2dpbiIsImV4cCI6MTY1NTMwODk4NywiaWF0IjoxNjU1MzA4ODY3LCJqdGkiOiI2OWIwNzg2ZC1lYjBmLTRjYWYtOTViNS1jYTVmODkyNDg3NjEiLCJoYXNoZWRDc3JmVG9rZW4iOiIxYzVjYzg4Y2Q0MjY3MDllNmI0Zjc0MjIzMDZmYTIyZGQxOTM4OWIyMmUzYWJlMWMzZDQzY2NkODhkMDE1OGEwIn0.go1We96p5ehEzV_RxuI_ZncCvE4teUB2nmy87DOFEEQISAS9gBXHjM0fB4VR1yP9-e_-nt-_5O3RsHyeSbRWJRxC_uu0Bu7RJGHR93IGVzs1OKzsGxJesExrIdvwKpQ2CcV0r7SJNiSm8XfxeuaPlBGSmlEzMeNCZWqOQIomRXvtNN9mpk3SgC4w3g6iskyW8L0dBauoJ_KmOjqmK8Oh7oGAZuQY-_abc-_7brDwxZnYnlCcf35mbNbGVlK_--qRaQldEKKCJ_s5MmVUabQ9_1fBTMiDBos-19j_XPjZZ8U61EgMDRB43DmxV12oOTUBbKSdtmd9KQ4W-jIui-W-xg) before I can access the remote repo
* make sure to go to `dev.lucid.preprod`, not `lucid.preprod`, to see changes

## Finding components 🔍
* look at the classes the component has and make sure the replacement component also can access them by updating the `.less` file
* find a component by going to the `dev site`, navigating somewhat towards the feature it is supposed to be in, then using the `clicking feature` in the *very top left corner* of the `inspect page`. 
    * if you just can't find a component, it could be a `feature flag`: which means it is a property that can be turned on and off.
    * in order to turn it on, go to https://admin.lucidpreprod.app/features and search up the feature name
    * you can find the feature name typically by looking at the surrounding `*ngif`, asking a dev, or looking at the `i18n.json` key for the `aria label`
* ** **take a screenshot of where to locate the fixed component and add it to your ticket** **
* **delete the old component from the `.html` file**

# Wrapping up a commit  ✔️
* you  can *squash* commits together using `git rebase -i HEAD~<number of commits you need to squash>`, then replacing the **first** word of the commit with the message you don't want to keep to `fixup` 
    * rebasing is super cool as it basically consolidates your commits into one commit of a branch, making the history look linear and easier to trace for bugs than if everything was branched out
    * in this case, we need to use the `-i` notation since it is a rebase ***internal*** to the branch, meaning you are consolidating one branch into itself rather than two separate branches together. 
    * `rebase` is better than `merge` once everything is cleaned up as it only contains a *history of the commits* rather than also having the `log` be saturated with unnecessary merge histories
