# Uncomment the next line to define a global platform for your project
platform :ios, '13.0'

plugin "cocoapods-binary-cache"

config_cocoapods_binary_cache(
  cache_repo: {
    "default" => {
      "local" => "~/.test-pods-cache/prebuilt-frameworks"
    }
  },
  bitcode_enabled: true,
  device_build_enabled: true
)

def binary_pod(name, *args, **kwargs)
  kwargs_cloned = kwargs.clone
  kwargs_cloned[:binary] = true if kwargs_cloned[:binary].nil?
  pod name, *args, **kwargs_cloned
end

target 'TestPods' do
  # Comment the next line if you don't want to use dynamic frameworks
  use_frameworks!

  # AMap sdk
  pod 'AMap2DMap-NO-IDFA', :binary => true
  pod 'AMapSearch-NO-IDFA', :binary => true
  pod 'AMapLocation-NO-IDFA', :binary => true
end
