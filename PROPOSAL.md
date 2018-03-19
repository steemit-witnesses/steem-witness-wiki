# steem-witness-wiki
Wiki for witness documentation

## Motivation 

When trying to setup a full node and a witness, I realized something. I know nothing. This is important because when you're new, you need a hub or a portal that you can go to for details to get you going. Witnesses all are there to help you out, but let's face it. We'd all like to be able to fish on our own. No one wants to be a burden.

This wiki does the following:
1. Provides a way for all witnesses to contribute
1. Reference for Witness API's
1. Reference for Witness commands.
1. Guides and Howto's for basic witness tasks
    * How to become a witness
    * Requirements for a seed node
    * Requirements for a full node
    * How to build a server
    * How to purchase a VPS
1. Links to Witness Updates
1. Portal for updates and information important to witnesses

One of the biggest advantages here is that it's not actually a wiki, but a digest. This forces updates to happen on a weekly basis. The information is vetted and updated weekly. There's no question if the information is relevant or accurate because it's checked every week and maintained by all witnesses.

# Requirements

Some of the requirements for this are:
1. All witnesses need to be able to contribute
1. Denied payout (possibly unless witnesses disagree with this requirement)
1. Feedback from communities
1. Pinnable to witness forums (steem.chat)
1. No central authority (community managed)

# Implementation

The wiki entry point is really a portal/landing page maintained in git. Witnesses can contribute to the wiki by submitting pull requests (PRs) to the [git repository](https://github.com/steemit-witnesses/steem-witness-wiki). 

> See the [Contribution Instructions](https://github.com/steemit-witnesses/steem-witness-wiki/blob/master/CONTRIBUTING.md)

## Process Flow
1. Each week, the wiki is branched. (Ex., 01-01-2018)
1. Witnesses can then modify the wiki (via PR) to add 
    * Witness Updates
    * New links
    * Link corrections
    * More guides
    * Reference updates
1. At the end of the week, a witness creates a PR to merge the weekly branch into the `publish` branch. (The witness can self-merge since the content has already been thoroughly PR'd up until this point)
1. Once the PR is merged, a github webhook fires on a separate service. This service will
    1. Pull the publish branch
    1. Publish to the Steem blockchain with the title (Witness Wiki (01-01-2018))
    1. The bot will then update the `comment_options` on the post setting one of the following:
        * Adding all witnesses as equal beneficiaries to the post
        * Reducing payout to 0 SBD denying payout.

## Template 

The wiki maintains a consistent format through a template. 