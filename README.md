# Governance Proposals Module

This module provides governance and voting capabilities for Open Social Groups, enabling democratic decision-making with treasury integration.

## Overview

The Governance Proposals module allows groups to create proposals, vote on them using off-chain signatures, and automatically execute approved proposals through the group's treasury. It supports multiple governance systems through a plugin architecture, with initial support for simple voting and optional Reality.eth integration for dispute resolution.

## Features

- **Proposal Management**: Create, view, and manage governance proposals within groups
- **Off-chain Voting**: Vote using EIP-712 signatures to avoid gas fees
- **Automatic Execution**: Approved budget proposals automatically create treasury transactions
- **Extensible Governance**: Plugin architecture for different voting systems
- **Real-time Tallying**: Live vote count updates with caching
- **Group Integration**: Seamless integration with Open Social Groups

## Dependencies

This module requires:
- Drupal 10.4.x
- Open Social 13.0.0-beta1
- Group module
- SIWE Login module
- Safe Smart Accounts module
- Group Treasury module

## Configuration

The module provides default settings for:
- Default voting period (7 days)
- Default approval threshold (51%)
- Reality.eth integration settings
- Minimum bond amounts for Reality questions

## Usage

Users with appropriate permissions can create proposals within groups, vote on active proposals, and track the status of proposals through their lifecycle. Administrators can configure governance settings at both the site and group level.

## Architecture

The module uses Drupal's entity system for storing proposals and votes, with services for vote aggregation, proposal execution, and integration with external systems like Reality.eth. The frontend uses ethers.js v6 for vote signing and real-time updates.