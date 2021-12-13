<table>
    <thead>
        <tr>
            <th>Benchmark Name</th>
            <th>Metrics</th>
            <th>ci</th>
            <th>2obj+H</th>
            <th>mod-2obj+h</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td rowspan=5>pybbs</td>
            <td>avg. objs per var</td>
            <td>196.3</td>
            <td>61.5</td>
            <td>40.8</td>
        </tr>
        <tr>
            <td>avg. objs per app var</td>
            <td>91.6</td>
            <td>33.4</td>
            <td><b>25.4</b></td>
        </tr>
        <tr>
            <td>edges (over ∼44K meths)</td>
            <td>397771</td>
            <td>304832</td>
            <td><b>278052</b></td>
        </tr>
        <tr>
            <td>app poly v-calls (of ∼2.4K)</td>
            <td>78</td>
            <td>66</td>
            <td>66</td>
        </tr>
        <tr>
            <td>app may-fail casts (of ∼8K)</td>
            <td>70</td>
            <td>54</td>
            <td><b>54</b></td>
        </tr>
        <tr>
            <td rowspan=5>shopizer</td>
            <td>avg. objs per var</td>
            <td><b>213.7</b></td>
            <td><b>59.0</b></td>
            <td>40.5</td>
        </tr>
        <tr>
            <td>avg. objs per var</td>
            <td><b>105.4</b></td>
            <td>17.6</td>
            <td>12.8</td>
        </tr>
        <tr>
            <td>edges (over ∼53K meths)</td>
            <td><b>445956</b></td>
            <td>333475</td>
            <td>313376</td>
        </tr>
        <tr>
            <td>app poly v-calls (of ∼25.6K)</td>
            <td><b>1254</b></td>
            <td>990</td>
            <td>983</td>
        </tr>
        <tr>
            <td>app may-fail casts (of ∼0.68K)</td>
            <td>703</td>
            <td>280</td>
            <td>267</td>
        </tr>
        <tr>
            <td rowspan=5>SpringBlog</td>
            <td>avg. objs per var</td>
            <td><b>113.4</b></td>
            <td>30.5</td>
            <td>16.9</td>
        </tr>
        <tr>
            <td>avg. objs per app var</td>
            <td><b>31.6</b></td>
            <td>9.1</td>
            <td>6.5</td>
        </tr>
        <tr>
            <td>edges (over ∼25K meths)</td>
            <td><b>187008</b></td>
            <td><b>142983</b></td>
            <td>130627</td>
        </tr>
        <tr>
            <td>app poly v-calls (of ∼0.73K)</td>
            <td>56</td>
            <td>48</td>
            <td>48</td>
        </tr>
        <tr>
            <td>app may-fail casts (of ∼0.04K)</td>
            <td><b>29</b></td>
            <td>14</td>
            <td>13</td>
        </tr>
        <tr>
            <td rowspan=5>WebGoat</td>
            <td>avg. objs per var</td>
            <td>34.2</td>
            <td>7.9</td>
            <td>5.5</td>
        </tr>
        <tr>
            <td>avg. objs per app var</td>
            <td>14.1</td>
            <td>2.9</td>
            <td>2.7</td>
        </tr>
        <tr>
            <td>edges (over ∼12K meths)</td>
            <td>71666</td>
            <td><b>58700</b></td>
            <td><b>55874</b></td>
        </tr>
        <tr>
            <td>app poly v-calls (of ∼1.6K)</td>
            <td>103</td>
            <td>87</td>
            <td>87</td>
        </tr>
        <tr>
            <td>app may-fail casts (of ∼0.04K)</td>
            <td><b>49</b></td>
            <td><b>28</b></td>
            <td><b>27</b></td>
        </tr>
    </tbody>
</table>
