# SKY Webhooks Tutorial (C#, .NET Core 8.0)

Working sample of the [SKY Developer Webhooks Tutorial](https://developer.blackbaud.com/skyapi/apis/webhook/tutorial). 

Please review the tutorial for more context for what this sample attempts to achieve.

## Prerequisites

- [.NET Core 8.0 SDK](https://dotnet.microsoft.com/en-us/download)
- Recommended: Visual Studio 2022 or [Visual Studio Code](https://code.visualstudio.com) 

## Background

This sample is based on the [Visual Studio ASP.NET Core Web Application (API) template](https://learn.microsoft.com/en-us/aspnet/core/tutorials/first-web-api?view=aspnetcore-8.0&preserve-view=true&tabs=visual-studio).

The code snippets from the SKY Developer Webhooks Tutorial have been compiled together into the WebhookController (`Controllers\WebhookController.cs`). Small modifications have been made to provide better logging and error handling. A business logic layer (`BusinessLogic\WebhookService.cs`) and Event Type classes have been added to demonstrate how a real service might choose to support multiple event types. This sample also makes use of the CloudEvents C# SDK rather than rolling our own CloudEvent class and deserialization.

## Running

- Clone or download this repo.
- Open the SkyWebhookTutorial project. (Command line to open in VS Code: `cd <your root>\sky-webhooks-csharp-tutorial\SkyWebhooksTutorial`, `code .`)
- Replace the value for `WebhookConfig.Key` in the `appsettings.json` with a unique value for you.
- Build and run the project. (Command line: `dotnet build`, `dotnet run`)

## Testing

At this point, your service should be running with your webhook handler at `https://localhost:5001/eventhandler?webhookKey=<your webhook key>`.

Review the [Test your endpoint](https://developer.blackbaud.com/skyapi/apis/webhook/tutorial#test-your-endpoint) section of the tutorial to test the your service's webhook handling capabilities.

## Subscribing to an event

In order to subscribe to a Blackbaud event, your service needs to be accessible to the public internet.

You can do this by [publishing your service to a hosting provider like Azure](https://docs.microsoft.com/en-us/aspnet/core/tutorials/publish-to-azure-webapp-using-vscode?view=aspnetcore-3.1#generate-the-deployment-package-locally).

Or you can use [ngrok](https://ngrok.com/) to make your locally running service publically accessible. If you choose to go this route, please clean up any subscriptions provisioned with temporary ngrok URLs.

## Questions

Please do not hesitate to reach out via the [Blackbaud Community](https://community.blackbaud.com/developer) with any questions you may have.