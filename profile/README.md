# Yarn.social

<img align="left" width="100" height="100" src="https://yarn.social/logo.png" style="padding-right: 5pt" />

[Yarn.social](https://yarn.social) is a decentralised self-hosted social media
that has a privacy-first focus.

There are **no** ads, **no** tracking and **no** personal information is ever collected or stored.

Read more [About Yarn.social](/about.html) or try the [Demo Pod](https://demo.yarn.social) today!

<a class="button" href="https://demo.yarn.social/">Try it Now!</a>

## 👉 Getting Started

Yarn.social is completely decentralized and operates on a "pull"-based model
unlike ActivityPub based platforms like Mastodon. In order to get onboard and
start following your friends, family or colleagues, you need a feed and a client.

You can either [Join an existing Pod](#join-an-existing-pod) that runs
Yarn.social's multi-user decentralised and distributed software called `yarnd`,
or you can [Run-a-pod](#run-a-pod) yourself on your own server or even a
Raspberry Pi! And finally you can [Manually](#manually) host your own feed and
use any "compatible" client of your choosing, or write a new one that implements
the [specifications](https://dev.twtxt.net). Enjoy 🤗

### 🤗 Join an existing Pod

You are welcome to join one of the existing pods listed here:

https://yarn.social/#join-an-existing-pod

**Note:** Due to increased spam and link submission bots and/or marketing/seo
type folks that don't know any better, _some_ pods have disabled "Open Registration".
If you'd like to join a pod that has registrations disabled, you'd best contact
its operator. An [Invite System](https://git.mills.io/yarnsocial/yarn/issues/695)
will be built soon™

### 📱 Mobile App

There is a native Mobile App for Yarn.social pods!

**NOTE:** The mobile app is being rebuilt and rebranded. Test versions can be found [here](https://twtxt.net/twt/uyrspdq)

### 🧶 Run a Pod

<a class="button" href="https://my.vultr.com/deploy?marketplace_app=yarn&marketplace_vendor_username=prologic">Deploy to Vultr!</a>

📣 **NEW:** (17th April 2022) [Yarn](https://my.vultr.com/deploy?marketplace_app=yarn&marketplace_vendor_username=prologic) is now available in the [Vultr](https://vultr.com) App Marketplace! See https://www.vultr.com/marketplace/apps/yarn for more details.

If you have [Docker](https://www.docker.com) installed and available to run containers you can run a `yarnd` instance by simply running:

```shell
$ docker run -p 8000:8000 prologic/yarnd
```

Pre-compiled binaries can be found on the [yarn Releases page](https://git.mills.io/yarnsocial/yarn/releases),
and are compiled by [James Mills](https://prologic.shortcircuit.net.au) and the `*-checksums.txt.sig` can be verified
with the GPG public key `C1F16643ADFF61B4A39EA3FEAC4C014F1440EBD6`.

Otherwise if you wish to compile from source and build `yarnd` yourself
(Be sure to have [Go](https://golang.org) installed):

```shell
$ git clone https://git.mills.io/yarnsocial/yarn
$ cd yarn
$ make deps
$ make
```

Now run your instance by running:

```shell
yarnd
```

For options see `yarnd --help`.

Please refer to the [Configuring your Pod](https://git.mills.io/yarnsocial/yarn/src/branch/master/README.md#configuring-your-pod)
guide for a production pod setup.

For other setups and community documentation on setting up a Yarn.social pod, please see [Our Pod Owner's WIki](https://git.mills.io/yarnsocial/yarn/wiki/), you are also welcome to contribute to the Wiki! 

### 💪 Manually

Since Yarn.social is built upon the [Twtxt](https://twtxt.readthedocs.org)
spec with a few [small (optional) extensions](https://dev.twtxt.net),
all you need to do to join the network and participate in the growing number
of users and conversations is have:

- Host a `twtxt.txt` file somewhere
- Add some important [Metadata](https://dev.twtxt.net/doc/metadataextension.html)
  such as `# Nick = `, `# Description = ` and `# Avatar =` at a minimum.
- Use a [twtxt](https://twtxt.readthedocs.org) Yarn-compatible client that
  at least implements the [Twt Subject Ext](https://dev.twtxt.net/doc/twtsubjectextension.html)
  and [Twt Hash Ext](https://dev.twtxt.net/doc/twthashextension.html) such as:
  - [jenny](https://uninformativ.de/git/jenny): A console twtxt client
    with [mutt](http://www.mutt.org) integration
    ([tutorial](https://www.uninformativ.de/blog/postings/2021-09-19/0/POSTING-en.html))
  - [jdtron/twet](https://github.com/jdtron/twet): A command-line client.
  - [twtr](https://git.envs.net/duriny/twtr): A twtxt client written in Go, for all your twting needs.

For the best experience your client _should_ also support some of the
[Twtxt Extensions](https://dev.twtxt.net) developed by Yarn.social's
development team and community. For example being able to participate in
"threads" by implementing the Twt Subject and Twt Hash extensions and the
Metadata extensions to advertise information about your feed such as a
description and avatar.

### 🌐 Hosting

> Coming soon™

## 👨‍🔧 Services

The following supporting services help to support the Yarn.social platform and
are provided for the benefit of all users:

- [search.twtxt.net](https://search.twtxt.net)
  This is an instance of the [Yarns](//git.mills.io/yarnsocial/yarn)
  search engine and crawls and indexes Yarn.social pods and Twtxt feeds.
- [feeds.twtxt.net](https://feeds.twtxt.net)
  This is an instance of [rss2twtxt](//git.mills.io/yarnsocial/rss2twtxt)
  and is used as the primary "feed source" for all Yarn.social pods (by default)
  and supports RSS/Atom and Twitter™. This allows users to "subscribe" to and "follow" websites, blogs or Twitter™ accounts.

## 💾 Sources

The project is managed by a self-hosted [Gitea](https://gitea.io) instance
at https://git.mills.io/yarnsocial

- [yarn](https://git.mills.io/yarnsocial/yarn)
  🧶 The `yarnd` self-hosted Yarn.social Pod server itself as well as the `yarnc` command-line client for posting and interacting with the `yarnd` API.
- [search](https://git.mills.io/yarnsocial/search)
  🔍 The Yarn.social search engine that crawls the network of pods and twtxt feeds, scrapes and indexes every twt.
- [feeds](https://git.mills.io/yarnsocial/feeds)
  📜 an RSS/Atom and Twitter feed aggregator that consumes RSS/Atom and Twitter™ feeds and produces twtxt feeds for consumption by Yarn.social pods as well as twtxt clients in general.
- [app](https://git.mills.io/yarnsocial/app)
  🐦 A Flutter iOS and Android App for the Yarn.social `yarnd` API to provide a native mobile experience for users (*in the process of being rebuilt*).

## 👨‍💻👩‍💻 Contributing

If you would like to help the project and contribute ideas, bug-fixes, improvements, etc, we're always looking for new contributors and we still have loads of things to do!

Please reach out to [@prologic](https://twtxt.net/user/prologic) or join our [Gitea](https://gitea.io) instance at https://git.mills.io/ and start filing issues and pull requests to the main project https://git.mills.io/yarnsocial/yarn

## 💬 Collaboration

We have an IRC channel `#yarn.social` on the [Libera.Chat](https://libera.chat/) IRC network. You are welcome to come chat to us and hang out.

## 🕵️‍♂️ Privacy and Abuse Policy

Yarn.social is a decentralised social media platform that supports micro-blogging (Twts) and full blogging. Pods (or individual instances) are owned and operators by "Pod Owners" or "Pod Operators". Pods can either be configured as single-user or multi-user (the default).

As such all Yarn.social pods share the following defaults Abuse and Privacy policies:

- [Default Abuse Policy (Community Guidelines)](/abuse.html)
- [Privacy Policy](/privacy.html)

__Note:__ The privacy policy applies to **ALL** Yarn.social pods as the software `yarnd` **DOES NOT** collect any personally identifiable information from users (**PII**), or any metadata or analytics of any kind nor does it send, sell or transfer any data from pods to any 3rd-parties.

## 👨‍⚖️ Licenses

Most of the software components here are licensed under the terms of the
[AGPL-3.0 License](https://opensource.org/licenses/AGPL-3.0) with the exception of
the hosting platform.
