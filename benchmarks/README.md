# STScript: Benchmarks

## Prerequisites
* [Node.js](https://nodejs.org/en/)
* npx -- `npm i -g npx`
* Make sure no processes are listening on ports 5000 and 8080 
  * For macOS/Linux users, run `sudo kill $(lsof -t -i :5000)` and `sudo kill $(lsof -t -i :8080)`
* `pbcopy`, used for running benchmarks
  * Installed by default on macOS
  * For Linux users, run `sudo apt-get install xclip -y && alias pbcopy='xclip -selection clipboard'`

## Running individual benchmarks
These instructions use the `bare` implementation of
the `simple_pingpong` variant -- change the directory name and apply the same steps to the other variants accordingly.

### Setup

Open two terminal windows at this working directory
```bash
cd simple_pingpong/bare
```

To prepare the client role for the benchmark,
```bash
# Build client
cd client
npm install
npm run build
```

In another terminal window,
to prepare the server role for the benchmark,
```bash
# Build server
cd server
npm install
npm run build

# Give permissions to benchmark script
chmod +x benchmark.sh
```

### Running the benchmarks

To run a benchmark for N round trips,
```bash
# Using the terminal window for the server
./benchmark.sh 100  # e.g. N = 100
```

```bash
# Using the terminal window for the client
npx serve -s build
```

Visit http://localhost:5000 on a web browser --
this will start the benchmark.
You can see the logs on the terminal window for the server.

Open the developer console on the web browser
and save a copy of the browser-side logs to
`simple_pingpong/bare/client/finelogs`.

Terminate the server process to obtain a copy of
the server-side logs in
`simple_pingpong/bare/server/finelogs`.

> Repeat these steps to run multiple benchmarks
> for the same configuration.

### Visualising benchmark results

Execute the cells in the `STScript-Benchmarks.ipynb`
notebook.
The easiest way is to open the notebook using
[Google Colab](https://colab.research.google.com/).