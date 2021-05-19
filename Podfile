ENV['SWIFT_VERSION'] = '5'

source 'https://github.com/CocoaPods/Specs.git'

platform :ios, '13.0'
use_frameworks!

def library
    pod 'KissXML'
    pod 'ICSMainFramework', :path => "./Library/ICSMainFramework/"
    pod 'MMWormhole'
    pod 'KeychainAccess'
end

def tunnel
    pod 'MMWormhole'
end

def socket
    pod 'CocoaAsyncSocket'
end

def model
    pod 'RealmSwift'
end

target "Potatso" do
    pod 'Aspects', :path => "./Library/Aspects/"
    pod 'Cartography'
    pod 'AsyncSwift'
    pod 'SwiftColor'
    pod 'Appirater'
    pod 'Eureka'
    pod 'MBProgressHUD'
#    pod 'CallbackURLKit', :path => "./Library/CallbackURLKit"
    pod 'CallbackURLKit'
    pod 'ICDMaterialActivityIndicatorView'
    # pod 'Reveal-iOS-SDK', '~> 1.6.2', :configurations => ['Debug']
    pod 'LookinServer', :configurations => ['Debug']
#    pod 'ICSPullToRefresh'
#    pod 'ICSPullToRefresh'
    pod 'ICSPullToRefresh', :git => "https://github.com/emukans/ICSPullToRefresh.Swift.git", :branch => "refactor/swift-5"
    pod 'ISO8601DateFormatter'
    pod 'Alamofire', '4.8.2'
    pod 'ObjectMapper', '~> 3.4'
    pod 'CocoaLumberjack/Swift'
    pod 'PSOperations'
    tunnel
    library
    socket
    model
end

target "PacketTunnel" do
    tunnel
    socket
end

target "PacketProcessor" do
    socket
end

target "TodayWidget" do
    pod 'Cartography'
    pod 'SwiftColor'
    library
    socket
    model
end

target "PotatsoLibrary" do
    library
    model
    # YAML-Framework 0.0.3 is not available in cocoapods so we install it from local using git submodule
    pod 'YAML-Framework', :path => "./Library/YAML-Framework"
end

target "PotatsoModel" do
    model
end

target "PotatsoLibraryTests" do
    library
end

#post_install do |installer|
#  installer.pods_project.targets.each do |target|
#    # Cache pod does not accept optimization level '-O', causing Bus 10 error. Use '-Osize' or '-Onone'
#    if target.name == 'Cache'
#      target.build_configurations.each do |config|
#        level = '-Osize'
#        config.build_settings['SWIFT_OPTIMIZATION_LEVEL'] = level
#        puts "Set #{target.name} #{config.name} to Optimization Level #{level}"
#      end
#    end
#  end
#end
#
#post_install do |installer|
#  installer.pods_project.targets.each do |target|
#    if target.name == 'CryptoSwift' || target.name == 'SwiftyBeaver'
#      target.build_configurations.each do |config|
#        config.build_settings['SWIFT_VERSION'] = '4.2'
#      end
#    end
#  end
#end
