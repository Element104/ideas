Vision: Secure by default and almost useful

The defaults for users
 * the goal is to have image, but we can start with scripts, it could be ansible
   * and what about the specfile (like we have fedora-minimal)
 * gnome or i3 -- big question
 * noscript feels so hard, let's use ublock
 * firefox in private mode
 * sudoers should be sane
 * selinux policy can perhaps be improved
   * a fallback to unconfined_t root may still be needed
   * multiuser (not single user)
 * pam namespaces
 * and what about rolekit, does it work?
 * basically xguest on drugs
   * xguest created new stuff for each session
   * we want to keep the previous sessions
