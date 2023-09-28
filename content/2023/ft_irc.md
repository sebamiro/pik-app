+++
title = "irc"
template = "project.html"
weight = 9
description = "-42 School project"
+++

<a target="blank" href="https://github.com/sebamiro/ft_irc">GitHub</a>

---

# IRC

## Summary

Is an group project about creating a small IRC server in C++98, that can be used with a
real IRC client to chat, create chat rooms, send private messages to one or multiple users,
via TCP connection.

Command list:
- PASS: Set a 'connection password'.
- NICK: Set or change user's nickname.
- USER: Set username, hostname and realname at the beginning of connection.
- MODE: Set or removes users or channels options.
- QUIT: Terminate a client session.
- JOIN: Request access to the given channel/s.
- PART: Remove user from the given channel/s.
- TOPIC: Change or view the topic of a channel.
- KICK: Request the forced removal of a user from a channel.
- PRIVMSG: Send private messages to other users or channels.

```
void
Server::quit(Client &client, const Parser::cmd_t &cmd)
{
	LOG_INFO("quit: " << client.getNickname() << " leaving")
	client.sendMsg("ERROR :Leaving Server");
	if (!cmd->args.empty()) {
		LOG_TRACE("quit: Reason: " << cmd->args.front())

		this->deleteClient(client.getFd(), cmd->args[0]);

		return;
	}
	LOG_TRACE("quit: No reason")
	this->deleteClient(client.getFd());
}	// Server::quit
```

## Introduction

Internet Relay Chat or IRC is a text-based communication protocol on the Internet.
It offers real-time messaging that can be either public or private. Users can exchange
direct messages and join group channels.

IRC clients connect to IRC servers in order to join channels. IRC servers are connected
together to form a network.

## Mandatory part

You have to develop an IRC server in C++ 98.

You mustn’t develop a client.
You mustn’t handle server-to-server communication.

Your executable will be run as follows:
```
./ircserv <port> <password>
```

- port: The port number on which your IRC server will be listening to for incoming
IRC connections.
- password: The connection password. It will be needed by any IRC client that tries
to connect to your server.

### Requirements

- The server must be capable of handling multiple clients at the same time and never
hang.
- Forking is not allowed. All I/O operations must be non-blocking.
- Only 1 poll() (or equivalent) can be used for handling all these operations (read,
write, but also listen, and so forth).
- Several IRC clients exist. You have to choose one of them as a reference. Your
reference client will be used during the evaluation process.
- Your reference client must be able to connect to your server without encountering
any error.
- Communication between client and server has to be done via TCP/IP (v4 or v6).
- Using your reference client with your server must be similar to using it with any
official IRC server. However, you only have to implement the following features:
  - You must be able to authenticate, set a nickname, a username, join a channel,
  send and receive private messages using your reference client.
  - All the messages sent from one client to a channel have to be forwarded to
  every other client that joined the channel.
  - You must have operators and regular users.
  - Then, you have to implement the commands that are specific to channel
  operators:
    - KICK - Eject a client from the channel
    - INVITE - Invite a client to a channel
    - TOPIC - Change or view the channel topic
    - MODE - Change the channel’s mode:
      - i: Set/remove Invite-only channel
      - t: Set/remove the restrictions of the TOPIC command to channel
      operators
      - k: Set/remove the channel key (password)
      - o: Give/take channel operator privilege
      - l: Set/remove the user limit to channe
  - Of course, you are expected to write a clean code.

## Bonus part

Here are the extra features you can add to your IRC server so it looks even more like and
actual IRC server:
- Handle file transfer.
- A bot.
