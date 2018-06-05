# :snowflake: Kotlin Branch Status

[`status.txt`](/status.txt) contains the list of locked branches in the [Kotlin](https://github.com/JetBrains/kotlin) project.

## File format

[`status.txt`](/status.txt) is a Java properties file. There are two kinds of key-value pairs there.

- Lines start with a `MESSAGE.` prefix contain a message to be displayed in the pre-push hook alert.  
Format: `MESSAGE.<message name> = <text>`  
`\n` is converted to the new line symbol.
- All other lines describe the locked branches.  
Format: `<branch name> = <message name>` (without the `MESSAGE.` prefix).

Of course, you can have multiple messages and multiple locked branches.

## Example

```
MESSAGE.1.2.40.blocked = We are releasing 1.2.41.
MESSAGE.1.2.50.blocked = 1.2.50 RC is out, and the branch has been stabilized.\nPush to it only if/when you got an approval (see #kotlin-release).
1.2.40 = 1.2.40.blocked
1.2.50 = 1.2.50.blocked
```

This means you have two locked branches (`1.2.40` and `1.2.50`) with different alert messages.
