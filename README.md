# Microsoft.Bot.Builder.FormFlow v4

netstandard2.0 port of https://github.com/Microsoft/BotBuilder/tree/master/CSharp/Library/Microsoft.Bot.Builder/FormFlow

**FormDialog inherits from ComponentDialog**

  - IDialog<T>.StartAsync changed to ComponentDialog.BeginDialogAsync
  
  - MessageReceived called by ComponentDialog.ContinueDialogAsync and .BeginDialogAsync

FormFlow dialogs can be added to a DialogSet:
```cs
_dialogs.Add(FormDialog.FromForm(SandwichOrder.BuildForm));
```
[SandwichOrder](https://github.com/EricDahlvang/Microsoft.Bot.Builder.FormFlow/blob/master/Sample/Microsoft.Bot.Builder.TestBot/Dialogs/SandwichOrder.cs#L36)
 > ported from v3 BotBuilder [SandwichOrder](https://github.com/Microsoft/BotBuilder/blob/master/CSharp/Samples/SimpleSandwichBot/Sandwich.cs#L33) FormFlow dialog

Or added to a component dialog:
```cs
public HotelsDialog() : base(nameof(HotelsDialog))
{
    var hotelsFormDialog = FormDialog.FromForm(this.BuildHotelsForm, FormOptions.PromptInStart);
    base.AddDialog(hotelsFormDialog);
}
```
[HotelsDialog](https://github.com/EricDahlvang/Microsoft.Bot.Builder.FormFlow/blob/master/Sample/Microsoft.Bot.Builder.TestBot/Dialogs/HotelsDialog.cs#L24)
 > ported from v3 BotBuilder-Samples [HotelsDialog](https://github.com/Microsoft/BotBuilder-Samples/blob/master/CSharp/core-MultiDialogs/Dialogs/HotelsDialog.cs) 


## Repository Instructions

After cloning:

- cd Microsoft.Bot.Builder.FormFLow
- git submodule init
- git submodule update --recursive --remote
- Open Microsoft.Bot.Builder.FormFlow.sln
- Set Microsoft.Bot.Builder.TestBot as StartUp Project

**Remote Dependencies**

  https://github.com/Microsoft/BotBuilder-dotnet
  
  https://github.com/EricDahlvang/nChronic/tree/netstandard2.0 
> (PR submitted: https://github.com/robertwilczynski/nChronic/pull/31 )

