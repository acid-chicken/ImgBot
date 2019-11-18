After you install Imgbot into your repo, this is registered with GitHub and you
are issued an _InstallationID_. Imgbot itself has an _ApplicationID_ and a
_private key_ that is kept secret. With a combination of the _InstallationID_,
the _ApplicationID_, and the _private key_, Imgbot can request an _Installation
Token_ from GitHub.

This _Installation Token_ is valid for 10 minutes at a time and provides the
permissions agreed to at the time of installation. If the permissions required
by Imgbot change you will be notified and have to accept before they can take
effect.

Imgbot specifically uses this _Installation Token_ to clone the repo, create a
branch, push a commit to the branch, and open pull requests. These actions are
performed on behalf of the installation with a username of 'x-access-token' and
a password set to the value of the _Installation Token_.

The author and committer for these actions are set to
`ImgBotApp<ImgBotHelp@gmail.com>`.

Furthermore, the commits pushed by Imgbot are digitally signed with a secure and
registered PGP private key and password and verified against a public key
registered with GitHub. This verification provides an extra level of security to
ensure that commits that come into your repo are in fact coming from the
authentic Imgbot. And you get the nice green verified badge in the PR.

If at anytime you want to remove Imgbot's ability to interact with your repo,
you simply uninstall the application from your settings and all further action's
will be immediately blocked with no access.

The following permissions are required for Imgbot to function:

- Write access to code
- Read access to metadata
- Read and write access to pull requests

The metadata access includes "Search repositories", "List collaborators", and
"Access repository metadata". See the
[GitHub documentation](https://developer.github.com/v3/apps/permissions/#metadata-permissions)
for more information.

The code access is required to clone the repo, create a branch, and push a
commit.

The pull requests access is required to open the actual pull request.
