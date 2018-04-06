
新版Air开发的app要加载非https网络资源,需要在-app.xml里增加以下几行才能上架

	 <iPhone>
     <Entitlements> 
      <![CDATA[ 
         <key>aps-environment</key> 
         <string>production</string> 
      ]]> 
   </Entitlements> 
   
        <InfoAdditions><![CDATA[
			<key>UIDeviceFamily</key>
			<array>
				<string>1</string>
				<string>2</string>
			</array>
		 	<key>MinimumOSVersion</key>
 		 	<string>9.0</string>
 		 
  		 	<key>NSAppTransportSecurity</key>
			<dict>
				<key>NSAllowsArbitraryLoads</key>
				<true/>
				<key>NSExceptionDomains</key>
					<dict>
					<key>yourserver.com</key>
						<dict>
							<!--Include to allow subdomains-->
							<key>NSIncludesSubdomains</key>
							<true/>
							<!--Include to allow HTTP requests-->
							<key>NSTemporaryExceptionAllowsInsecureHTTPLoads</key>
							<true/>
							<!--Include to specify minimum TLS version-->
							<key>NSTemporaryExceptionMinimumTLSVersion</key>
							<string>TLSv1.1</string>
						</dict>
					</dict>
			</dict>
		]]></InfoAdditions>
        <requestedDisplayResolution>high</requestedDisplayResolution>
   	 </iPhone>
    
    
    以上并不是每一条都要用上,仅供参考,具体意思查询adobe网站吧,简单来说全部复制过去用是没问题的
