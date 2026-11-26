<div align="center">

# no-slop

**Comments that explain *why*, not *what*.**

An agent skill that stops AI coding assistants from littering your code with comments nobody asked for.

[![License: MIT](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)
[![Stars](https://img.shields.io/github/stars/fsystemweb/no-slop?style=flat)](https://github.com/fsystemweb/no-slop/stargazers)
[![Agent Skill](https://img.shields.io/badge/agent-skill-blueviolet)](skills/no-slop/SKILL.md)

</div>

---

## The problem

You ask an AI to write a function. You get this:

```ts
// Function to get active users
function getActiveUsers(users: User[]): User[] {
  // Create an empty array to store active users
  const result: User[] = [];

  // Loop through each user
  for (const user of users) {
    // Check if the user is active
    if (user.isActive) {
      // Add the user to the result array
      result.push(user);
    }
  }

  // Return the result
  return result;
}
```

## With no-slop

```ts
const getActiveUsers = (users: User[]) => users.filter((user) => user.isActive);
```

Same behavior. Zero noise. When a comment does appear, it earns its place:

```ts
// Stripe rejects retries inside 24h of a failed charge, so back off first.
await sleep(RETRY_BACKOFF_MS);
```

## Install

**Claude Code**

```
/plugin marketplace add fsystemweb/no-slop
/plugin install no-slop --marketplace fsystemweb/no-slop
```

**Any agent that supports skills** (Cursor, Codex, Gemini CLI, and more)

```sh
npx skills add fsystemweb/no-slop
```

**Manually**

```sh
git clone https://github.com/fsystemweb/no-slop
cp -r no-slop/skills/no-slop ~/.claude/skills/
```

## What it enforces

- No comments that narrate operations, loops, conditions, or returns
- No step-by-step walkthroughs, section banners, or change-log notes
- No restating what names, types, tests, or docstrings already say
- Better names and smaller functions before reaching for a comment
- Comments only for business rules, constraints, workarounds, and non-obvious edge cases
- A final pass that deletes every comment adding no context

The whole policy is one short file: [`SKILL.md`](skills/no-slop/SKILL.md).

## Contributing

Found a slop pattern the skill misses? [Open an issue](https://github.com/fsystemweb/no-slop/issues) or send a PR. Keep it short. This skill should stay as lean as the code it asks for.

## License

[MIT](LICENSE)
