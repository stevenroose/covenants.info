+++
title = "Congestion Control"
description = "Overview of the congestion control use case for Bitcoin Covenants."
draft = false
weight = 60
sort_by = "weight"
template = "docs/page.html"

[extra]
lead = ""
toc = true
top = false
+++


##### Links

- [blog post](https://rubin.io/bitcoin/2021/12/09/advent-12/)


## Introduction

Congestion Control is a way for a user who wants to make a large number of transactions in a period
of high fees, make a single transaction that commits to all the individual desired transactions in a
way that they can be later executed when fees are lower. The commitment ensures that all the
eventual transactions will be made, which gives the receivers of these transactions full certainty
that their transaction can at all times be confirmed if they are willing to pay the required fee.


## Proposals

While Congestion Control was published explicitly as a use case for [CTV](/proposals/ctv), it
is a form of [transaction templating](/use-cases/tx-templating) and hence can be achieved with
any other proposal that enables this.


