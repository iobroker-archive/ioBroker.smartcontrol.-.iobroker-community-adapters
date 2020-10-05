In contrast to the table above, you can use so-called "enums" here - [Link to documentation: Enums](https://www.iobroker.net/#en/documentation/admin/enums.md).
<br>You can assign a "function" (`enum.functions`) in each row, and limit this to certain rooms (`enum.rooms`) if wanted. All states containing the function (and optionally the room) are switched once a trigger is being activated and the conditions in the zones are fulfilled.
<br><strong>Please note</strong> that all states to which you have assigned the respective function require the same data type (i.e. boolean - true/false, or string), since 'Value for 'on'` and 'Value for 'off'` applies to all states to which the selected function is assigned. But don't worry, the adapter will show an error in the log if your assignment does not fit ;-)

Translated with www.DeepL.com/Translator (free version)

| Column | Mandatory | Description |
|----------|:------------:|-------|
| ![image](https://github.com/Mic-M/ioBroker.smartcontrol/blob/master/admin/doc-md/img/check_box-24px.svg?raw=true) |  Yes   | Enables/disables this table row. If not activated, this table row is ignored by the adapter. In the Adapter Options, under 'FURTHER OPTIONS > Input Validation', you can set that even disabled rows are checked for validity. |
| Name | Yes   | Name of your choice. Forbidden characters: ``[ ] * , ; ' " ` < > \ ?`` |
| Enum Function Name |    Yes   | Select the according function of the enumerations ([enum details are described here](https://www.iobroker.net/#en/documentation/admin/enums.md)). As soon as a zone is triggered in which you have selected this table row under 'Target Devices', all states to which this selected "function" is assigned will be switched. |
| Limit to rooms | No | Here you can optionally limit to certain "rooms" (`enum.rooms`): if one or more rooms are selected here, the targets will only be switched if one of these rooms is assigned to the target state of the selected function. If you leave it empty, no rooms will be checked. |
| Value for 'on' | Yes | States value that is set in 'states to switch on'. You can use `true`, `false`, numbers like `144`, or strings like `Turn on radio`. All spaces and quotation marks (like `"`) at the beginning and end are automatically removed. <br><br>The value can be overwritten under "4. ZONES", "Target devices". |
| Do not verify (on) | No | Before switching, it is always verified if the target device is already on according to "Value for 'on'". Activating this option disables this verification, and switching is always done. Use case: e.g. a button as a state. See [Github Issue #5](https://github.com/Mic-M/ioBroker.smartcontrol/issues/5). |
| Value for 'off' | Yes | States value to be set in 'Switch off state'. You can use `true`, `false`, numbers like `144`, or strings like `turn radio on`. All spaces and quotation marks (like `"`) at the beginning and end are automatically removed.|
| Do not verify (off) | No | See *Value for 'on'* above, bot for switching off, and not on. |