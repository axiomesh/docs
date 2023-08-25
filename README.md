# Axiomesh Docs

The Axiomesh docs project, we put everything you should know about `Axiomesh` here.

## 👩‍💻 Development

Install the [Mintlify CLI](https://www.npmjs.com/package/mintlify) to preview the documentation changes locally. To install, use the following command

```
npm i -g mintlify
```

Run the following command at the root of your documentation (where mint.json is)

```
mintlify dev
```

### 🙋🏻Issues

`mintlify dev` will automatically download client in `~/.mintlify/mint/client`, and then build soft links.
If you encounter some issues running the command, please do the following steps to check:

- do you have the dir `~/.mintlify/mint/client`, if not, that means you encountered an internet error,
  it has may be caused by many reasons such as GFW. Try to run the command elsewhere and
  download the `~/.mintlify` dir local.
- `~/.mintlify/mint/client` is not empty, run
    ```shell
    mintlify install
    ```
  may fix the issue. It will download npm packages and build links. If you encounter an internet error here, try
  to reset the npm registry：
    ```shell
    npm config set registry https://registry.npmjs.org/
    ```
  and try `mintlify install` again.

Overall, if you encounter any internet issue, the fastest way is to run the command elsewhere and
download the `~/.mintlify` dir to local.

## 😎 Publishing Changes

Changes will be deployed automatically after pushing to the default branch.

You can also preview changes using PRs, which generates a preview link of the docs.

### Troubleshooting

- Page loads as a 404 - Make sure you are running in a folder with `mint.json`
- some new features, such as latex support may need a high version, please check your version `mintlify -v`. We build
  the project from 3.0.98, you can do the following step to update mintlify:
    ```shell
   rm -rf ~/.mintlify # remove client, in case version mismatch
   nvm use 19 # new version need node 19
   node install mintlify@latest # or some specific version
    ```
