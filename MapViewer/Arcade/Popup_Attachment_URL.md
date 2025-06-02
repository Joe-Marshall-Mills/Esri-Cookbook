var P1 = "https://services6.arcgis.com/_ITEMID_/arcgis/rest/services/* *LAYERNAME* */FeatureServer/0/"
var ObjectID = $feature.FIELD
var P2 = "/attachments/"
var AttachID = $feature.FIELD

P1 + ObjectID + P2 + AttachID
