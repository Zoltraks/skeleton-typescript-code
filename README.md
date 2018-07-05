README
======

This is a skeleton for **TypeScript** code and **Visual Studio Code** project.

Quick start
-----------

Create source file with *.ts extension for your program.

Start either with **npm install** or **npm init**.

```
npm init
```

As entry point specify created *.ts file or leave default **index.js**. This may be specified later in **package.json** configuration.

```json
{
  "devDependencies": {
    "ts-node": "^7.0.0",
    "typescript": "^2.9.2"
  },
  "name": "program1",
  "description": "Create source file with *.ts extension.",
  "version": "1.0.0",
  "main": "program1.ts",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "author": "",
  "license": "ISC"
}
```

Now **npm** will do the job for finishing our setup environment for *TypeScript* and *Visual Studio Code*.

```
npm install
```

You may want to check if everything works nice with simple *TypeScript* code like in following example. Make some breakpoints, hit **F5** button and check what happens.

```ts
class Hello
{
    public static hello() : void
    {
        console.log("Hello");
        console.log("World");        
    }
}

Hello.hello();
```

If everything works fine, you should see something like this on your **DEBUG CONSOLE**.

```
node.exe -r ts-node/register --inspect-brk=43977 program1.ts 
Debugger listening on ws://127.0.0.1:43977/8e32e369-5a48-4345-a6f7-59edbf326780
Hello
World
```

If any breakpoint is hit you may also see lines like this, and **Visual Studio Code** will allow you to continue program execution. **Debug \ Step Over** is your friend now.

```
program1.ts:5
```

In case of any error, you may want to check your **.vscode/launch.json**.

```json
{
    // Use IntelliSense to learn about possible attributes.
    // Hover to view descriptions of existing attributes.
    // For more information, visit: https://go.microsoft.com/fwlink/?linkid=830387
    "version": "0.2.0",
    "configurations": [
        {
            "type": "node",
            "request": "launch",
            "name": "Launch Program",
            "protocol": "inspector",
            "args": ["${relativeFile}"],
            "cwd": "${workspaceRoot}",
            "runtimeArgs": ["-r", "ts-node/register"],
            "internalConsoleOptions": "openOnSessionStart",
            "outFiles": [
                "${workspaceFolder}/**/*.js"
            ]
        }
    ]
}
```
