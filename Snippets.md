## Template Argument Example
```xslt
<xsl:if test="($firstClass) and (@first = 1)”>
	<xsl:value-of select="$firstClass" />
</xsl:if>
```

## Template Manifest
```xml
<?xml version="1.0" encoding="utf-8" ?>
<manifest>
	<template>tokens.txt</template>

	<scripts>
		<script>myScript.js</script>
	</scripts>

	<stylesheets>
		<stylesheet>stylesheet.css</stylesheet>
	</stylesheets>

	<defaultClientOptions>
		<clientOption type="string"			name="bestConference"		value="DNNCon" />
		<clientOption type="number"			name="theAnswerToLife"		value="42" />
		<clientOption type="boolean"		name="toBooleanOrNot"		value="true" />
	</defaultClientOptions>

	<defaultTemplateArguments>
		<templateArgument type="string"		name="whoToFollowOnTwitter"	value="@theleewise" />
		<templateArgument type="number"		name="gorillaWeightLbs"		value="10" />
		<templateArgument type="boolean"	name="isBenCoolerThanLee"	value="false" />
	</defaultTemplateArguments>
</manifest>
```

## Options in Skin Object
```ASP
<ddr:Menu MenuStyle="..." NodeSelector="..." runat="server">
	<TemplateArguments>
		<ddr:TemplageArgument Name="whoToFollowOnTwitter" Value="@theleewise" />
		<ddr:TemplageArgument Name="gorillaWeightLbs" Value="10" />
		<ddr:TemplageArgument Name="isBenCoolerThanLee" Value="false" />
	</TemplateArguments>
	<ClientOptions>
			<ddr:ClientString Name="bestConference" Value="DNNCon" />
			<ddr:ClientNumber Name="theAnswerToLife" Value="42" />
			<ddr:ClientBoolean Name="toBooleanOrNot" Value="true" />
	</ClientOptions>
</ddr:Menu>
```

## Client Options in Template (Tokens)
```javascript
<script type="text/javascript">
	;(function($){
		var clientOptions = "[=Options]";
		clientOptions = clientOptions.replace(/&quot;/g,"\"");
		clientOptions = eval("("+clientOptions+")");
		$(".class-name").YourPlugin(clientOptions);
	})(jQuery);
</script>
```

## Client Options in Template (XSLT)
```xslt
<script type="text/javascript">
	var clientOptions = <xsl:value-of select="$Options" />;
	$(".class-name").YourPlugin(clientOptions);
</script>
```