# GeminiProChat

Minimal web UI for GeminiPro Chat.

Live demo: [Gemini Pro Chat](https://www.geminiprochat.com)

[![image](https://github.com/babaohuang/GeminiProChat/assets/559171/d02fd440-401a-410d-a112-4b10935624c6)](https://www.geminiprochat.com)

## Acknowledgements

This project is inspired by and based on the following open-source project:

- [ChatGPT-Demo](https://github.com/anse-app/chatgpt-demo) - For the foundational codebase and features.


## Running Locally

### Pre environment
1. **Node**: Check that both your development environment and deployment environment are using `Node v18` or later. You can use [nvm](https://github.com/nvm-sh/nvm) to manage multiple `node` versions locally.

   ```bash
    node -v
   ```

2. **PNPM**: We recommend using [pnpm](https://pnpm.io/) to manage dependencies. If you have never installed pnpm, you can install it with the following command:

   ```bash
    npm i -g pnpm
   ```

3. **GEMINI_API_KEY**: Before running this application, you need to obtain the API key from Google. You can register the API key at [https://makersuite.google.com/app/apikey](https://makersuite.google.com/app/apikey).

### Getting Started

1. Install dependencies

   ```bash
    pnpm install
   ```

2. Copy the `.env.example` file, then rename it to `.env`, and add your [GEMINI API key](https://makersuite.google.com/app/apikey) to the `.env` file.

   ```bash
    GEMINI_API_KEY=AIzaSy...
   ```

3. Run the application, the local project runs on `http://localhost:3000/`

   ```bash
    pnpm run dev
   ```

## Environment Variables

You can control the website through environment variables.

| Name | Description | Required |
| --- | --- | --- |
| `GEMINI_API_KEY` | Your API Key for GEMINI. You can get it from [here](https://makersuite.google.com/app/apikey).| **Yes** |
| `API_BASE_URL` | Custom base url for GEMINI API. Click [here](https://github.com/babaohuang/GeminiProChat?tab=readme-ov-file#solution-for-user-location-is-not-supported-for-the-api-use) to see when to use this. | No |
| `HEAD_SCRIPTS` | Inject analytics or other scripts before `</head>` of the page | No |
| `PUBLIC_SECRET_KEY` | Secret string for the project. Use for generating signatures for API calls | No |
| `SITE_PASSWORD` | Set password for site, support multiple password separated by comma. If not set, site will be public | No |

## Deploy

### Deploy With Vercel(Recommended)

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https://github.com/babaohuang/GeminiProChat&env=GEMINI_API_KEY&envDescription=Google%20API%20Key%20for%20GeminiProChat&envLink=https://makersuite.google.com/app/apikey)

Just click the button above and follow the instructions to deploy your own copy of the app.

> [!NOTE]
> #### Solution for "User location is not supported for the API use"
> If you encounter the issue **"User location is not supported for the API use"**, follow these steps to resolve it:
>
> 1. Go to this [**palm-proxy**](https://github.com/antergone/palm-proxy) repo and click **"Deploy With Vercel"**.
> 2. Once the deployment is complete, you will receive a domain name assigned by Vercel (e.g., `https://xxx.vercel.app`).
> 3. In your **Gemini Pro Chat** project, set an environment variable named `API_BASE_URL` with the value being the domain you got from deploying the gemini proxy (`https://xxx.vercel.app`).
> 4. Redeploy your **Gemini Pro Chat** project to finalize the configuration. This should resolve the issue.
>
> Thanks to [**antergone**](https://github.com/antergone/palm-proxy) for providing this solution.

### Deploy With Docker

Although this project provides a Dockerfile, there is currently a known bug with the Docker deployment method. I am actively working on fixing this issue. Therefore, Docker deployment is not recommended at this moment. If any contributors have a solution to fix this bug, your contributions are highly welcomed. Please feel free to submit a Pull Request (PR) to help me resolve this issue.

## Star History

[![Star History Chart](https://api.star-history.com/svg?repos=babaohuang/geminiprochat&type=Timeline)](https://star-history.com/#babaohuang/geminiprochat&Timeline)