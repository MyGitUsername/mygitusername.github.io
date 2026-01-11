---
layout: post
title:  "BEAM Overview (Notes from a talk by Saša Jurić)"
date:   2022-01-23
---
The following notes and diagrams are from [a live talk] [yt-talk] by Saša Jurić,
the author of "Elixir in Action", given at GOTO 2019.  

BEAM (the Erlang virtual machine) is the runtime layer for 
several languages including Erlang, Elixir, LFE, Alpaca, Gleam.  

A process in BEAM terminology is a runtime execution context of code; it 
is not an OS process and it is not an OS thread. It is a sequential program without concurrency.  

To become concurrent you need to run multiple processes. There are a lot of ways to do this in Elixir.
For example:

```
...
spawn(fn -> ... end)
...
```

Spawn starts a new process. Separate processes run in parallel; they are completely different 
programs running completely separately from each other with their own separate stack, heap, 
execution, separate garbage collection, etc.  

Separate processes work together, cooperate by sending messages. This is called message passing concurrency.
In Elixir, the most foundational way to do this is with `send/2`.    

<table>
  <tr>
    <th> process A </th>
    <th> process B </th>
  </tr>
  <tr>
    <td>
<pre>
send(process_b, some_message)
</pre>
    </td>
    <td>
<pre>
receive do
  message ->
    handle(message)
  end
</pre>
    </td>
  </tr>
</table>


When you invoke a command to start an Elixir system (i.e., a project with some file hierarchy with a 
bunch of source files) a single OS process is started, your own instance of BEAM, the Erlang virtual machine. 
The entire system is running within this OS process and within this OS process there 
are bunch of small, sequential, independent, lightweight programs -- processes that spawn from within your code. 
Processes are quite cheap in terms of memory and startup and time. You are going to have bunch of processes, on the order of 
hundreds of thousands, millions -- we really run a lot of them. Internally, BEAM employs OS threads called schedulers, 
by default one scheduler per available CPU core. The schedulers are responsible for executing these processes. As a naive mental model,
imagine we have a single queue of processes pending for execution: each scheduler somehow pulls a process from the queue, 
runs it for a little while, puts it at the end of the queue, takes the next one from queue, rinse and repeat.

<br/>
![Beam Diagram](/assets/images/beam-diagram.png)


<br/>
<br/>
Source: [The Soul of Erlang and Elixir • Saša Jurić • GOTO 2019] [yt-talk]  

[yt-talk]: https://www.youtube.com/watch?v=JvBT4XBdoUE  
