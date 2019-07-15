new Calendar(<Calendar element>,aOptionInputObj)
->
aOptionInputObj --> new OptionManager(aOptionInputObj) -> OptionManager.overrides = Obj

--> Calendar.optionManager
->
Calendar.handleOption(optionManager.computed)
->
this.viewSpecs = buildViewSpecs(
      pluginHooks.views,
      this.optionsManager
    )
->
buildViewSpecs(defaultInputs,optionsManager)
->
let overrideConfigs = parseViewConfigs(optionsManager.overrides.views)
->
let viewDefs = compileViewDefs(defaultConfigs, overrideConfigs)

mapHash(viewDefs, function(viewDef) {
    return buildViewSpec(viewDef, overrideConfigs, optionsManager)
})

//////////
Abstract time grid view .ts
this.dayGrid.limitRows(eventLimit)

/////
renderDayRowHtml(row, isRigid)

//////
 unlimitRow(row)


 ////
 problem now
 -> not work with drag -> if drag it will return to collapsed