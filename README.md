# Docker-RNNTagger
Docker Container as a wrapper for RNNTagger with easy to use API. You can watch the documentation for RNNTagger here: [Link](https://www.cis.uni-muenchen.de/~schmid/tools/RNNTagger/).

This tool is not designed for use in a producitve environment. It is a simple workaround for having a simple to use API to access RNNTagger. You might encounter a bad performance from this, it
 is NOT gpu accelerated.

## Installation

Because the license of RNNTagger forbids the redistribution of itself I am not able to share the docker image with you.

Unfortunately you have to build the container yourself with this easy steps:

1. Create a folder on your linux system with docker
2. Copy the `Dockerfile` there
3. Run in the same folder: `docker build --no-cache -t imagename .` (change imagename to your desired image name

Afterwards you simply can run the container with `docker run -d -p 80:8080 imagename`. Change the port according to your needs. You might want to use docker compose for this.

## Endpoints

### GetTags

Tags all words and stemms them to their root word.

Url: `/gettags`

**Parameters (GET)**

lang: Language to tag

string: your text to stemm

**Returns**

Returns a List with sentences, sentences are lists with a dict for each word with `original`, `tag` and `root`.

### GetTags (POST))

Tags all words and stemms them to their root word. Uses JSON encoding. This endpoint is easier to use for heavy requests.

Url: `/gettags`

**Parameters (POST)**

Use json formatting!

lang: Language to tag

string: your text to stemm

**Returns**

Returns a List with sentences, sentences are lists with a dict for each word with `original`, `tag` and `root`.


### GetLangs

List all available languages.

Url: `/getlangs`

**Return**

Returns a list of languages available.
