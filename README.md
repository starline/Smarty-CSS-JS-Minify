
```
use GoodGin\Libs\SmartyCombine\Combine;

$this->smarty->registerPlugin(Smarty::PLUGIN_FUNCTION, 'combine', [$this, 'combine_function']);
    
/**
 * CSS JS Combine
 * @param array $params
 */
public function combine_function(array $params)
{
    // Default params
    $params['use_true_path'] = false;
    $params['debug'] = isset($params['debug']) ? $params['debug'] : $this->Config->smarty_combine_debug;
    $params['age'] = 60 * 60 * 24; # seconds
    $params['cache_dir'] = $this->Config->root_dir . 'var/combine/' . $this->theme;

    return Combine::init($params);
}
```


