```$xslt

getter
#if($field.modifierStatic)
static ##
#end
$field.type ##
#set($name = $StringUtil.capitalizeWithJavaBeanConvention($StringUtil.sanitizeJavaIdentifier($helper.getPropertyName($field, $project))))
#if ($field.boolean && $field.primitive)
is##
#else
get##
#end
${name}() {
if($field.name != null){
return ($field.type)$field.name .clone();
}
return null;
}

setter
#set($paramName = $helper.getParamName($field, $project))
#if($field.modifierStatic)
static ##
#end
void set$StringUtil.capitalizeWithJavaBeanConvention($StringUtil.sanitizeJavaIdentifier($helper.getPropertyName($field, $project)))($field.type $paramName) {
#if ($field.name == $paramName)
    #if (!$field.modifierStatic)
    ##this.##
    #else
        $classname.##
    #end
#end
if($paramName!= null){
this. $field.name= ($field.type)$paramName .clone();
}else{
this. $field.name =null ;
}
}
```