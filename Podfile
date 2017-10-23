# 下面行是指明依赖库的来源地址
source 'https://github.com/CocoaPods/Specs.git'
# 说明平台是ios，版本是9.0
platform :ios, '9.0'
# 忽略引入库的所有警告（强迫症者的福音啊）
inhibit_all_warnings!
# 如果使用use_frameworks!命令会在Pods工程下的Frameworks目录下生成依赖库的framework
#use_frameworks!

# 针对 RxReSwiftTrans target引入
target 'RxReSwiftTrans' do
  # 如果使用use_frameworks!命令会在Pods工程下的Frameworks目录下生成依赖库的framework
  use_frameworks!
  
  pod 'RxSwift', '~> 4.0'
  pod 'RxCocoa', '~> 4.0'
  pod 'Action', '~> 3.4.0'
  pod 'RxDataSources', '~> 3.0.1'
  pod 'RealmSwift', '~> 3.0'
  pod 'RxRealm', '~> 0.7.3'
  pod 'NSObject+Rx', '~> 4.1.0'

end

# enable tracing resources
post_install do |installer|
	installer.pods_project.targets.each do |target|
		if target.name == 'RxSwift'
			target.build_configurations.each do |config|
				#config.build_settings['CONFIGURATION_BUILD_DIR'] = '$PODS_CONFIGURATION_BUILD_DIR'
				if config.name == 'Debug'
					config.build_settings['OTHER_SWIFT_FLAGS'] ||= ['-D',
					'TRACE_RESOURCES']
				end
			end
		end
	end
end
