# Gator

Gator is a command-line RSS feed aggregator built with TypeScript and PostgreSQL.

It allows users to register, follow RSS feeds, aggregate posts, and browse the latest posts from the feeds they follow.

## Requirements

To run Gator, you need:

- Node.js
- npm
- PostgreSQL

## Setup

1. Clone the repository.

2. Install dependencies:

   npm install

3. Create a PostgreSQL database named `gator`.

4. Create a configuration file in your home directory:

   ~/.gatorconfig.json

Example:

{
  "db_url": "postgres://postgres:YOUR_PASSWORD@localhost:5432/gator?sslmode=disable",
  "current_user_name": ""
}

5. Run the database migrations:

   npx drizzle-kit migrate

## Running Gator

Run commands using:

npm run start <command> [arguments]

## Commands

Register a user:

npm run start register <username>

Log in:

npm run start login <username>

List users:

npm run start users

Add an RSS feed:

npm run start addfeed "<feed-name>" "<feed-url>"

List feeds:

npm run start feeds

Follow a feed:

npm run start follow "<feed-url>"

Unfollow a feed:

npm run start unfollow "<feed-url>"

List followed feeds:

npm run start following

Start the feed aggregator:

npm run start agg 1m

Browse the latest posts:

npm run start browse

You can optionally specify the number of posts:

npm run start browse 5

Reset the database:

npm run start reset

## Stopping the Aggregator

The `agg` command runs continuously.

Press Ctrl+C to stop it.
