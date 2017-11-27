# s7_forum

> A Vue.js project

## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report

# run unit tests
npm run unit

# run all tests
npm test
```
## Data setup
_SQL relation_

- categories:
-- has_many: forums
- forums
-- has_many: threads
- moderators
- posts
-- belongs_to: users, threads
- stats
- threads
-- has_many: contributors, posts
-- belongs_to: user, forum
- users
-- has_many(not available in the data): posts, threads

"""json
{
    "categories": {
        <categories_key>: {
            "forums": {
                <forum_key>: <forum_key>
                <forum_key>: <forum_key>
            }
            "name": <name>,
            "slug": <slug>,
            ".key": <categories_key>
        }
    },
    "forums": {
        <forum_key>: {
            "categoryId": <category_key>,
            "description": <description>,
            "lastPostId": <last_post_id>,
            "name": <name>,
            "slug": <slug>,
            "threads": {
              <thread_id>: <thread_id>
            },
            ".key": <forum_key>
        }
    },
    "moderators": {
        <moderator_key>: <moderator_key>
    },
    "posts": {
      <post_id>: {
        "edited": {
          "at": 1504037546,
          "by": "ALXhxjwgY9PinwNGHpfai6OWyDu2",
          "moderated": false
        },
        "publishedAt": 1504035908,
        "text": <text>,
        "threadId": <thread_id>,
        "userId": <user_id>,
        ".key": <post_id>
      }
    },
    "stats": {
      "postsCount": 23,
      "threadsCount": 5,
      "usersCount": 14,
      "usersOnline": 0
    },
    "threads": {
      <thread_id>: {
        "contributors": {
            <contributor_id>: <contributor_id>
        },
        "firstPostId": <first_post_id>,
        "forumId": <forum_id>,
        "lastPostAt": <last_post_at>,
        "lastPostId": <last_post_id>,
        "posts": {
            <post_id>: <post_id>
        },
        "publishedAt": 1504035908,
        "slug": "what-kind-of-pet-do-you-have",
        "title": "What kind of pet do you have?",
        "userId": <user_id>,
        ".key": <thread_id>
      }
    }  
    "users": {
      <user_id>: {
        "avatar": <img_url>,
        "email": "chrisvfritz@gmail.com",
        "lastVisitAt": 1504772078,
        "name": "Chris Fritz",
        "registeredAt": 1504632260,
        "username": "chrisvfritz",
        "usernameLower": "chrisvfritz",
        ".key": <user_id>
      },
}
"""