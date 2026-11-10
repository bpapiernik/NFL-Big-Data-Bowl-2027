# NFL-Big-Data-Bowl-2027

<div class="dataset-readme">
  <h1>Dataset Description</h1>
  <h2>Overview of Datasets</h2>
  <p>The competition dataset contains high-frequency optical tracking, standardized physical testing results, and multi-season NFL game performance metrics for 510 rookie prospects drafted or signed between 2023 and 2025.</p>
  <p>The dataset is partitioned into 9 CSV files (~2.2 GiB total) linking pre-draft physical traits directly to regular-season on-field outcomes.</p>
  <section>
    <h3>File 1: <code>players.csv</code></h3>
    <p>Contains demographic, collegiate, and draft metadata for the 510 rookie prospects.</p>
    <table>
      <thead>
        <tr><th>Column Name</th><th>Data Type</th><th>Example</th><th>Description</th></tr>
      </thead>
      <tbody>
        <tr><td><code>nfl_id</code></td><td>int64</td><td><code>55867</code></td><td>Unique identifier assigned to each NFL player. Primary key across all tracking and performance tables.</td></tr>
        <tr><td><code>display_name</code></td><td>str</td><td><code>Will Anderson</code></td><td>Player&#x27;s full legal name as registered with the NFL.</td></tr>
        <tr><td><code>draft_year</code></td><td>int64</td><td><code>2023</code></td><td>Year the prospect entered the NFL Draft (2023, 2024, or 2025).</td></tr>
        <tr><td><code>nfl_position</code></td><td>str</td><td><code>DE</code></td><td>Official NFL roster position (e.g., WR, CB, T, G, C, DT, DE, OLB, TE, SS, FS, NT, DB, ILB, MLB, RB, FB).</td></tr>
        <tr><td><code>birth_date</code></td><td>str</td><td><code>2001-09-02</code></td><td>Player date of birth in YYYY-MM-DD format.</td></tr>
        <tr><td><code>college_name</code></td><td>str</td><td><code>Alabama</code></td><td>College or university where the prospect played prior to entering the draft.</td></tr>
        <tr><td><code>college_conference</code></td><td>str</td><td><code>Southeastern Conference</code></td><td>NCAA athletic conference of the prospect&#x27;s collegiate team.</td></tr>
        <tr><td><code>draft_round</code></td><td>int64 / null</td><td><code>1</code></td><td>Round in which the player was selected (1–7). null for Undrafted Free Agents (UDFAs).</td></tr>
        <tr><td><code>draft_pick_within_round</code></td><td>int64 / null</td><td><code>3</code></td><td>Pick number within the specific draft round. null for UDFAs.</td></tr>
        <tr><td><code>draft_overall_pick</code></td><td>int64 / null</td><td><code>3</code></td><td>Overall pick selection number across the entire draft (1–259+). null for UDFAs.</td></tr>
      </tbody>
    </table>
  </section>
  <section>
    <h3>File 2: <code>combine_results.csv</code></h3>
    <p>Contains official anthropometric measurements, standardized physical testing splits, and Next Gen Stats draft grades from the NFL Scouting Combine.</p>
    <table>
      <thead>
        <tr><th>Column Name</th><th>Data Type</th><th>Example</th><th>Description</th></tr>
      </thead>
      <tbody>
        <tr><td><code>draft_year</code></td><td>int64</td><td><code>2023</code></td><td>Year of the Scouting Combine (2023, 2024, 2025).</td></tr>
        <tr><td><code>nfl_id</code></td><td>int64</td><td><code>56040</code></td><td>Unique player identifier matching players.csv.</td></tr>
        <tr><td><code>combine_position</code></td><td>str</td><td><code>TE</code></td><td>Position group the prospect participated with during Combine drills.</td></tr>
        <tr><td><code>combine_height</code></td><td>float64</td><td><code>77.875</code></td><td>Official prospect height measured in inches (e.g., 77.875 = 6&#x27;5.875&quot;).</td></tr>
        <tr><td><code>combine_weight</code></td><td>int64</td><td><code>245</code></td><td>Official prospect body weight measured in pounds (lbs).</td></tr>
        <tr><td><code>hand_size</code></td><td>float64</td><td><code>10.0</code></td><td>Hand span measured from tip of thumb to tip of pinky in inches.</td></tr>
        <tr><td><code>arm_length</code></td><td>float64</td><td><code>32.25</code></td><td>Arm length measured from acromion to tip of middle finger in inches.</td></tr>
        <tr><td><code>wing_span</code></td><td>float64</td><td><code>79.75</code></td><td>Total fingertip-to-fingertip wingspan in inches.</td></tr>
        <tr><td><code>ten_yd_split</code></td><td>float64</td><td><code>1.60</code></td><td>Official electronic 10-yard split time during the 40-yard dash in seconds.</td></tr>
        <tr><td><code>forty</code></td><td>float64</td><td><code>4.84</code></td><td>Official electronic 40-yard dash time in seconds.</td></tr>
        <tr><td><code>vertical</code></td><td>float64</td><td><code>38.5</code></td><td>Standing vertical jump height in inches.</td></tr>
        <tr><td><code>broad_jump</code></td><td>float64</td><td><code>125.0</code></td><td>Standing broad jump distance in inches.</td></tr>
        <tr><td><code>three_cone</code></td><td>float64</td><td><code>7.12</code></td><td>3-cone (L-drill) agility time in seconds (contains null for drill opt-outs).</td></tr>
        <tr><td><code>short_shuttle</code></td><td>float64</td><td><code>4.25</code></td><td>20-yard short shuttle (5-10-5) agility time in seconds (contains null for opt-outs).</td></tr>
        <tr><td><code>bench_reps</code></td><td>float64</td><td><code>22.0</code></td><td>Number of 225 lb bench press repetitions completed (contains null for opt-outs).</td></tr>
        <tr><td><code>ngs_athleticism_score</code></td><td>int64</td><td><code>60</code></td><td>Next Gen Stats composite athleticism score (0–100 percentile scale).</td></tr>
        <tr><td><code>ngs_college_production_score</code></td><td>float64</td><td><code>78.2</code></td><td>Next Gen Stats college production score based on college statistics.</td></tr>
        <tr><td><code>ngs_final_score</code></td><td>float64</td><td><code>74.5</code></td><td>Next Gen Stats overall prospect score combining athleticism and college production.</td></tr>
      </tbody>
    </table>
  </section>
  <section>
    <h3>File 3: <code>combine_tracking.csv</code></h3>
    <p>Contains 10 Hz high-frequency optical sensor tracking across 6,310 Combine drill attempts, including 40-yard dash sprints and position-specific agility/route drills.</p>
    <table>
      <thead>
        <tr><th>Column Name</th><th>Data Type</th><th>Example</th><th>Description</th></tr>
      </thead>
      <tbody>
        <tr><td><code>draft_year</code></td><td>int64</td><td><code>2025</code></td><td>Year of Combine testing (2023, 2024, 2025).</td></tr>
        <tr><td><code>event_id</code></td><td>str</td><td><code>2025030210...</code></td><td>Unique identifier linking all tracking frames within a single continuous drill attempt.</td></tr>
        <tr><td><code>nfl_id</code></td><td>int64 / null</td><td><code>58286</code></td><td>Player identifier matching players.csv. For ball, it represents the nfl_id for player in given event_id.</td></tr>
        <tr><td><code>entity_type</code></td><td>str</td><td><code>PLAYER</code></td><td>Entity tracked in the frame: PLAYER or BALL.</td></tr>
        <tr><td><code>time</code></td><td>str</td><td><code>2025-03-02T18:56:38.200</code></td><td>ISO 8601 timestamp for the optical tracking frame (sampled every 0.10 seconds).</td></tr>
        <tr><td><code>drill_type</code></td><td>str</td><td><code>SKILL_DRILLS_OL</code></td><td>Broad drill category (e.g., FORTY_YARD_DASH, THREE_CONE_DRILL, SHORT_SHUTTLE, SKILL_DRILLS_WR, SKILL_DRILLS_DB, SKILL_DRILLS_OL, SKILL_DRILLS_DL, SKILL_DRILLS_TE).</td></tr>
        <tr><td><code>drill_name</code></td><td>str</td><td><code>OL_PULL_DRILL_FOLD...</code></td><td>Specific drill name (e.g., GAUNTLET_DRILL, RUN_THE_HOOP_DRILL, BACK_PEDAL_AND_TRANSITION_45_DEGREE_REACTION, SLOT_STRIKE_ROUTE_LEFT, PASS_PRO_MIRROR_DRILL).</td></tr>
        <tr><td><code>attempt</code></td><td>int64</td><td><code>4</code></td><td>Attempt number index for the prospect within the given drill.</td></tr>
        <tr><td><code>x</code></td><td>float64</td><td><code>87.09</code></td><td>Player horizontal position along field length in yards (0-120).</td></tr>
        <tr><td><code>y</code></td><td>float64</td><td><code>22.52</code></td><td>Player vertical position across field width in yards (0-53.33).</td></tr>
        <tr><td><code>s</code></td><td>float64</td><td><code>0.28</code></td><td>Instantaneous player speed in yards per second (yd/s).</td></tr>
        <tr><td><code>a</code></td><td>float64</td><td><code>0.11</code></td><td>Instantaneous player acceleration in yards per second squared (yds / sec^2).</td></tr>
        <tr><td><code>dis</code></td><td>float64</td><td><code>0.01</code></td><td>Distance traveled from the previous tracking frame in yards.</td></tr>
        <tr><td><code>dir</code></td><td>float64</td><td><code>126.08</code></td><td>Player motion direction angle in degrees (0-360).</td></tr>
      </tbody>
    </table>
  </section>
  <section>
    <h3>File 4: <code>player_career_successes.csv</code></h3>
    <p>Contains cumulative career volume statistics, snap counts, and accolades earned by the 510 prospects during their rookie and subsequent seasons.</p>
    <table>
      <thead>
        <tr><th>Column Name</th><th>Data Type</th><th>Example</th><th>Description</th></tr>
      </thead>
      <tbody>
        <tr><td><code>nfl_id</code></td><td>int64</td><td><code>55867</code></td><td>Unique player identifier matching players.csv.</td></tr>
        <tr><td><code>career_offensive_snaps</code></td><td>int64</td><td><code>0</code></td><td>Cumulative career offensive snaps played across regular-season and playoff games.</td></tr>
        <tr><td><code>career_defensive_snaps</code></td><td>int64</td><td><code>1884</code></td><td>Cumulative career defensive snaps played across regular-season and playoff games.</td></tr>
        <tr><td><code>career_special_teams_snaps</code></td><td>int64</td><td><code>92</code></td><td>Cumulative career special teams snaps played.</td></tr>
        <tr><td><code>career_games_active</code></td><td>int64</td><td><code>51</code></td><td>Total number of regular-season games the player was on the active roster.</td></tr>
        <tr><td><code>career_games_started</code></td><td>int64</td><td><code>44</code></td><td>Total number of regular-season games started by the player.</td></tr>
        <tr><td><code>ap_all_pro_1st_team</code></td><td>int64</td><td><code>1</code></td><td>Total number of Associated Press (AP) First-Team All-Pro selections earned in career.</td></tr>
        <tr><td><code>ap_all_pro_2nd_team</code></td><td>int64</td><td><code>0</code></td><td>Total number of Associated Press (AP) Second-Team All-Pro selections earned in career.</td></tr>
        <tr><td><code>pro_bowl_original_ballot</code></td><td>int64</td><td><code>1</code></td><td>Total number of Pro Bowl selections on the original ballot (excluding alternate injury replacements).</td></tr>
      </tbody>
    </table>
  </section>
  <section>
    <h3>File 5: <code>player_play.csv</code></h3>
    <p>Contains granular in-game Next Gen Stats and play-by-play metrics for every snap involving the rookie cohort across the 2023, 2024, and 2025 seasons (N = 316,338 player-play records).</p>
    <h4>A. Play Context &amp; Identifiers</h4>
    <table>
      <thead>
        <tr><th>Column Name</th><th>Data Type</th><th>Example</th><th>Description</th></tr>
      </thead>
      <tbody>
        <tr><td><code>game_id</code></td><td>int64</td><td><code>2023091801</code></td><td>Unique 10-digit game identifier matching games.csv.</td></tr>
        <tr><td><code>play_id</code></td><td>int64</td><td><code>56</code></td><td>Unique play identifier within the game.</td></tr>
        <tr><td><code>team_abbr</code></td><td>str</td><td><code>BAL</code></td><td>3-letter abbreviation of the team the player is on.</td></tr>
        <tr><td><code>nfl_id</code></td><td>int64</td><td><code>55976</code></td><td>Unique player identifier matching players.csv.</td></tr>
        <tr><td><code>lined_up_position</code></td><td>str</td><td><code>T</code></td><td>Position where the player aligned on this specific play (e.g., WR, CB, T, G, C, DE, DT, TE, FS, SS, OLB).</td></tr>
        <tr><td><code>play_description</code></td><td>str</td><td><code>(15:00) P.Mahomes pass...</code></td><td>Official textual play-by-play description of the play.</td></tr>
        <tr><td><code>quarter</code></td><td>int64</td><td><code>1</code></td><td>Quarter of the game (1, 2, 3, 4, or 5 for overtime).</td></tr>
        <tr><td><code>down</code></td><td>int64</td><td><code>1</code></td><td>Current down (1, 2, 3, 4).</td></tr>
        <tr><td><code>yards_to_go</code></td><td>int64</td><td><code>10</code></td><td>Yards needed to achieve a first down or touchdown.</td></tr>
        <tr><td><code>possession_team</code></td><td>str</td><td><code>CLE</code></td><td>3-letter abbreviation of the offensive team.</td></tr>
        <tr><td><code>yardline_side</code></td><td>str</td><td><code>CLE</code></td><td>3-letter abbreviation of the team side of the field where the ball is spotted.</td></tr>
        <tr><td><code>yardline_number</code></td><td>int64</td><td><code>25</code></td><td>Distance in yards to the nearest goal line (1 ≤ yardline ≤ 50).</td></tr>
        <tr><td><code>game_clock</code></td><td>str</td><td><code>15:00</code></td><td>Game clock remaining in the quarter in MM:SS format.</td></tr>
        <tr><td><code>pre_snap_home_score</code></td><td>int64</td><td><code>0</code></td><td>Home team score prior to the snap.</td></tr>
        <tr><td><code>pre_snap_visitor_score</code></td><td>int64</td><td><code>0</code></td><td>Visiting team score prior to the snap.</td></tr>
        <tr><td><code>play_direction</code></td><td>str</td><td><code>left</code></td><td>Direction of offensive play progression (left or right).</td></tr>
      </tbody>
    </table>
    <h4>B. Win Probability &amp; Expected Points</h4>
    <table>
      <thead>
        <tr><th>Column Name</th><th>Data Type</th><th>Example</th><th>Description</th></tr>
      </thead>
      <tbody>
        <tr><td><code>pre_snap_home_team_win_probability</code></td><td>float64</td><td><code>0.4237</code></td><td>Home team estimated win probability prior to snap.</td></tr>
        <tr><td><code>pre_snap_visitor_team_win_probability</code></td><td>float64</td><td><code>0.5763</code></td><td>Visiting team estimated win probability prior to snap.</td></tr>
        <tr><td><code>home_team_win_probability_added</code></td><td>float64</td><td><code>0.2210</code></td><td>Change in home team win probability produced by the play.</td></tr>
        <tr><td><code>visitor_team_win_probility_added</code></td><td>float64</td><td><code>-0.2210</code></td><td>Change in visiting team win probability produced by the play.</td></tr>
        <tr><td><code>expected_points_added</code></td><td>float64</td><td><code>-8.459</code></td><td>Net Expected Points Added (EPA) generated on the play.</td></tr>
        <tr><td><code>expected_points</code></td><td>float64</td><td><code>1.459</code></td><td>Expected points value of the offensive drive state prior to snap.</td></tr>
      </tbody>
    </table>
    <h4>C. Schemes, Formations &amp; Play Results</h4>
    <table>
      <thead>
        <tr><th>Column Name</th><th>Data Type</th><th>Example</th><th>Description</th></tr>
      </thead>
      <tbody>
        <tr><td><code>offense_formation</code></td><td>str</td><td><code>EMPTY</code></td><td>Offensive pre-snap personnel formation (e.g., SHOTGUN, SINGLEBACK, EMPTY, I_FORM, PISTOL, JUMBO).</td></tr>
        <tr><td><code>receiver_alignment</code></td><td>str</td><td><code>3x2</code></td><td>Wide receiver alignment distribution (e.g., 3x1, 2x2, 3x2, 1x1, 4x1).</td></tr>
        <tr><td><code>pass_result</code></td><td>str</td><td><code>IN</code></td><td>Outcome of the pass play: C (Complete), I (Incomplete), S (Sack), IN (Interception), R (Scramble).</td></tr>
        <tr><td><code>pass_length</code></td><td>float64</td><td><code>5.0</code></td><td>Air yards traveled by the pass past the line of scrimmage (negative for passes behind the LOS).</td></tr>
        <tr><td><code>play_nullified_by_penalty</code></td><td>str</td><td><code>N</code></td><td>Y if the play outcome was wiped out by penalty, N otherwise.</td></tr>
        <tr><td><code>penalty_yards</code></td><td>float64</td><td><code>null</code></td><td>Total penalty yardage enforced on the play.</td></tr>
        <tr><td><code>pre_penalty_yards_gained</code></td><td>int64</td><td><code>0</code></td><td>Gross yards gained before penalty assessment.</td></tr>
        <tr><td><code>yards_gained</code></td><td>int64</td><td><code>0</code></td><td>Official net yards gained on the play.</td></tr>
        <tr><td><code>team_coverage_man_zone</code></td><td>str</td><td><code>ZONE_COVERAGE</code></td><td>Primary defensive coverage scheme classification (MAN_COVERAGE, ZONE_COVERAGE).</td></tr>
        <tr><td><code>team_coverage_type</code></td><td>str</td><td><code>COVER_6_ZONE</code></td><td>Specific defensive coverage shell (e.g., COVER_1, COVER_2, COVER_3, COVER_4, COVER_6_ZONE, COVER_0, PREVENT).</td></tr>
        <tr><td><code>in_motion_at_ball_snap</code></td><td>bool</td><td><code>False</code></td><td>True if the player was in active pre-snap motion when the ball was snapped.</td></tr>
      </tbody>
    </table>
    <h4>D. Receiver &amp; Ball Carrier Metrics</h4>
    <table>
      <thead>
        <tr><th>Column Name</th><th>Data Type</th><th>Example</th><th>Description</th></tr>
      </thead>
      <tbody>
        <tr><td><code>target</code></td><td>bool</td><td><code>False</code></td><td>True if the player was the intended target of the pass.</td></tr>
        <tr><td><code>rec_yards</code></td><td>float64</td><td><code>14.0</code></td><td>Receiving yards gained by the player on the play.</td></tr>
        <tr><td><code>rush_yards</code></td><td>float64</td><td><code>null</code></td><td>Rushing yards gained by the player on the play.</td></tr>
        <tr><td><code>yards_after_catch</code></td><td>float64</td><td><code>6.2</code></td><td>Yards gained by the receiver after securing the catch (YAC).</td></tr>
        <tr><td><code>fumble</code></td><td>float64</td><td><code>0.0</code></td><td>1.0 if the player fumbled the ball on the play, 0.0 otherwise.</td></tr>
        <tr><td><code>fumble_lost</code></td><td>float64</td><td><code>0.0</code></td><td>1.0 if the player&#x27;s fumble was recovered by the opponent.</td></tr>
        <tr><td><code>route_ran</code></td><td>str</td><td><code>SLANT</code></td><td>Specific route run by the receiver (e.g., GO, OUT, SLANT, CROSS, POST, CORNER, HITCH, SCREEN, FLAT, WHEEL).</td></tr>
        <tr><td><code>separation_at_pass_forward</code></td><td>float64</td><td><code>2.84</code></td><td>Distance in yards to the nearest defender at the moment the ball is thrown forward.</td></tr>
        <tr><td><code>cushion</code></td><td>float64</td><td><code>6.15</code></td><td>Pre-snap distance in yards between the receiver and their primary coverage defender.</td></tr>
        <tr><td><code>expected_yards_after_catch</code></td><td>float64</td><td><code>4.1</code></td><td>Next Gen Stats expected yards after catch model prediction at catch moment.</td></tr>
      </tbody>
    </table>
    <h4>E. Offensive Line &amp; Pass Protection Metrics</h4>
    <table>
      <thead>
        <tr><th>Column Name</th><th>Data Type</th><th>Example</th><th>Description</th></tr>
      </thead>
      <tbody>
        <tr><td><code>dropback_duration</code></td><td>float64</td><td><code>1.835</code></td><td>Time from snap to pass release, sack, or pressure in seconds.</td></tr>
        <tr><td><code>extended_sack_allowed</code></td><td>float64</td><td><code>0.0</code></td><td>Sacks allowed on extended dropbacks exceeding 4.0 seconds.</td></tr>
        <tr><td><code>pass_rushers_encountered</code></td><td>float64</td><td><code>1.0</code></td><td>Number of distinct pass rushers engaged by the offensive lineman on the play.</td></tr>
        <tr><td><code>peak_pressure_probability_allowed</code></td><td>float64</td><td><code>0.1975</code></td><td>Peak estimated pressure probability allowed by the offensive lineman.</td></tr>
        <tr><td><code>pressure_allowed</code></td><td>bool</td><td><code>False</code></td><td>True if the offensive lineman allowed a pressure (QB hurry, hit, or sack).</td></tr>
        <tr><td><code>sack_allowed</code></td><td>float64</td><td><code>0.0</code></td><td>Sacks charged to the offensive lineman (1.0 for solo, 0.5 for shared).</td></tr>
        <tr><td><code>time_to_pressure_allowed</code></td><td>float64</td><td><code>2.45</code></td><td>Time in seconds from snap until the offensive lineman allowed pressure.</td></tr>
      </tbody>
    </table>
    <h4>F. Defensive Pass Rush &amp; Tackle Metrics</h4>
    <table>
      <thead>
        <tr><th>Column Name</th><th>Data Type</th><th>Example</th><th>Description</th></tr>
      </thead>
      <tbody>
        <tr><td><code>blitzing</code></td><td>bool</td><td><code>False</code></td><td>True if the defender was rushing the passer on a blitz.</td></tr>
        <tr><td><code>player_get_off</code></td><td>float64</td><td><code>0.742</code></td><td>Time in seconds from ball snap until defensive rusher moves forward across the line of scrimmage.</td></tr>
        <tr><td><code>sack</code></td><td>float64</td><td><code>1.0</code></td><td>1.0 if the defender recorded a sack on the play (0.5 for shared sack).</td></tr>
        <tr><td><code>tackle</code></td><td>float64</td><td><code>1.0</code></td><td>1.0 if the defender made a solo tackle on the ball carrier.</td></tr>
        <tr><td><code>assist</code></td><td>float64</td><td><code>0.0</code></td><td>1.0 if the defender assisted on a tackle.</td></tr>
        <tr><td><code>caused_forced_fumble</code></td><td>float64</td><td><code>0.0</code></td><td>1.0 if the defender forced a fumble on the play.</td></tr>
        <tr><td><code>recovered_fumble</code></td><td>float64</td><td><code>0.0</code></td><td>1.0 if the player recovered a loose fumble.</td></tr>
        <tr><td><code>tackle_for_loss</code></td><td>float64</td><td><code>1.0</code></td><td>1.0 if the tackle stopped the play behind the line of scrimmage for negative yards.</td></tr>
        <tr><td><code>time_to_pressure</code></td><td>float64</td><td><code>2.18</code></td><td>Time elapsed from snap until this defender generated pressure on the quarterback.</td></tr>
        <tr><td><code>time_to_qb_hurry</code></td><td>float64</td><td><code>2.80</code></td><td>Time elapsed from snap until this defender forced a QB hurry.</td></tr>
        <tr><td><code>coverage_assignment</code></td><td>str</td><td><code>MAN</code></td><td>Pre-snap coverage assignment (e.g., MAN, DEEP_THIRD, FLAT, HOOK_CURL).</td></tr>
        <tr><td><code>coverage_assignment_at_snap</code></td><td>str</td><td><code>MAN</code></td><td>Coverage responsibility updated at ball snap following pre-snap motion.</td></tr>
        <tr><td><code>quick_pressure</code></td><td>float64</td><td><code>null</code></td><td>1.0 if a pass rusher pressures within 2.50 seconds of the snap.</td></tr>
        <tr><td><code>unblocked_pressure</code></td><td>float64</td><td><code>null</code></td><td>1.0 if a pass rusher pressured the QB through this lineman&#x27;s gap without being blocked.</td></tr>
      </tbody>
    </table>
  </section>
  <section>
    <h3>File 6: <code>games.csv</code></h3>
    <p>Contains schedule, season, and team matchup metadata for all 1,002 NFL regular-season and playoff games across 2023, 2024, and 2025.</p>
    <table>
      <thead>
        <tr><th>Column Name</th><th>Data Type</th><th>Example</th><th>Description</th></tr>
      </thead>
      <tbody>
        <tr><td><code>game_id</code></td><td>int64</td><td><code>2023090700</code></td><td>Unique 10-digit NFL game identifier (YYYYMMDD##). Primary key.</td></tr>
        <tr><td><code>game_key</code></td><td>int64</td><td><code>59173</code></td><td>Historical NFL game key identifier.</td></tr>
        <tr><td><code>season</code></td><td>int64</td><td><code>2023</code></td><td>NFL season year (2023, 2024, 2025).</td></tr>
        <tr><td><code>season_type</code></td><td>str</td><td><code>REG</code></td><td>Type of season: REG (Regular Season) or POST (Playoffs).</td></tr>
        <tr><td><code>week</code></td><td>int64</td><td><code>1</code></td><td>Week number within the season (Weeks 1–18).</td></tr>
        <tr><td><code>home_team_abbr</code></td><td>str</td><td><code>KC</code></td><td>3-letter abbreviation of the home team.</td></tr>
        <tr><td><code>visitor_team_abbr</code></td><td>str</td><td><code>DET</code></td><td>3-letter abbreviation of the visiting team.</td></tr>
      </tbody>
    </table>
  </section>
  <section>
    <h3>Files 7, 8, 9: <code>game_tracking_2023.csv</code>, <code>game_tracking_2024.csv</code>, <code>game_tracking_2025.csv</code></h3>
    <p>Contain 10 Hz high-frequency in-game optical tracking frames for all rookie cohort prospects across each respective NFL season.</p>
    <table>
      <thead>
        <tr><th>Column Name</th><th>Data Type</th><th>Example</th><th>Description</th></tr>
      </thead>
      <tbody>
        <tr><td><code>game_id</code></td><td>int64</td><td><code>2024080952</code></td><td>Game identifier matching games.csv.</td></tr>
        <tr><td><code>play_id</code></td><td>int64</td><td><code>3379</code></td><td>Play identifier matching player_play.csv.</td></tr>
        <tr><td><code>nfl_id</code></td><td>int64</td><td><code>57367</code></td><td>Player identifier matching players.csv (tracks all 510 rookie cohort prospects).</td></tr>
        <tr><td><code>time</code></td><td>str</td><td><code>2024-08-10T01:30:31.800</code></td><td>ISO 8601 timestamp for the in-game optical tracking frame (sampled every 0.10s).</td></tr>
        <tr><td><code>x</code></td><td>float64</td><td><code>87.09</code></td><td>Player horizontal position along field length in yards (0-120).</td></tr>
        <tr><td><code>y</code></td><td>float64</td><td><code>22.52</code></td><td>Player vertical position across field width in yards (0-53.33).</td></tr>
        <tr><td><code>s</code></td><td>float64</td><td><code>0.28</code></td><td>Instantaneous player speed in yards per second (yd/s).</td></tr>
        <tr><td><code>a</code></td><td>float64</td><td><code>0.11</code></td><td>Instantaneous player acceleration in yards per second squared (yds / sec^2).</td></tr>
        <tr><td><code>dis</code></td><td>float64</td><td><code>0.03</code></td><td>Distance traveled from the previous tracking frame in yards.</td></tr>
        <tr><td><code>o</code></td><td>float64</td><td><code>98.51</code></td><td>Player body orientation angle in degrees (0-360).</td></tr>
        <tr><td><code>dir</code></td><td>float64</td><td><code>126.08</code></td><td>Player motion direction angle in degrees (0-360).</td></tr>
        <tr><td><code>event</code></td><td>str / null</td><td><code>pass_forward</code></td><td>Game play milestone event tag (e.g., ball_snap, pass_forward, pass_arrived, tackle, touchdown, first_contact, out_of_bounds, or null for regular frames).</td></tr>
      </tbody>
    </table>
  </section>
</div>
