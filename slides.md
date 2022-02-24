---
# try also 'default' to start simple
theme: penguin
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: https://source.unsplash.com/collection/94734566/1920x1080
# https://sli.dev/custom/highlighters.html
highlighter: shiki
# show line numbers in code blocks
lineNumbers: false
layout: presenter
eventLogo: './assets/cn_logo.jpeg'
eventUrl: 'https://twitter.com/QUTCode/photo'
twitter: '@taiga_matsu_'
twitterUrl: 'https://twitter.com/taiga_matsu_'
presenterImage: './assets/presenter.JPG'
---
# Taiga Matsumoto
Hello CN Fellows 👋
- QUT grad from Bachelor of IT and major in CS 🧑‍💻
- From Japan 🍣
- Currently working for Fupay as a software engineer
- Dog person 🐶

---
layout: text-image
media: './assets/screen-1.png'
---

# Most recent work: Codemoon

[Codemoon](https://codemoon.net) is a website builder powered by visual programming

- 🧱 **Blockly** - A visual programming editor used in an application called Blockly, which is developed by Google and used by many different applications like Scratch
- 🚀 **Deployable** - A user is able to deploy a website they built as easy as press a few buttons! This feature is powered by GCP 
---
layout: text-image
media: './assets/blockly-example.gif'
---

# Blockly

- A user just drags and drops a block listed on left lane to workspace.
- Many users, who do not have many programming experiences said this is more fun to code than typing on an text editor.
---
layout: text-window
---

# Deployment

- Deployment feature is powered by GCP and fast api
- When a service receives a request from a client to deploy, it uploads html as a static file to Cloud Storage, and return an endpoint of a static file on Storage to a client as a response.

::window::

```py
async def create_html_deployment(html: Html) -> str:
  ...
  # Upload to Cloud Storage
  bucket = storage_client.get_bucket('...')
  blob = bucket.blob(unique_html_filename)
  blob.upload_from_string(decoded, content_type='text/html')
  # Return a url to deployed website to a client
  public_url = f"https://storage.googleapis.com/{unique_html_filename}"
  return public_url
```
