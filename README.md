# cors-policy-laravel-angular
Cors policy laravel angular

execute commande to add middleware: php artisan make:middleware CorsPolicy; for create new middleware


add this line into $routeMiddleware table in kernel.php: <strong>\App\Http\Middleware\CorsPolicy::class,</strong>

Update handle fonction in CorsPolicy.php by:<br/>
<strong>$headers = [
            'Access-Control-Allow-Origin' => '*',
            'Access-Control-Allow-Headers' => 'Content-Type, X-Auth-Token, Origin, Authorization',
        ];<br/>
        $response = $next($request);<br/>
        foreach ($headers as $key => $value) <br/>
        {<br/>
            $response->header($key, $value);<br/>
        }<br/>
        return $response;
</strong>
